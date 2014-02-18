Rule #1: Do incremental migrations 
----------------------------------

Migrations which involve changes to schema and data are slow, especially on big tables. The best strategy is to limit the scope of your migrations to one change at a time, so that the migration can run as quickly as possible and minimise downtime.  

But rules are made to be broken...
-------------------------------

Sometimes the nature of the change to your model structure necessitates multiple migrations that need to occur at once. For example, if I want to standardize multiple models by using an abstract base model.

class Book(models.Model):
    
    author = models.ForeignKey(Author)
    book_title = models.CharField(max_length=1000)
    page_count = models.IntegerField()

        
class Magazine(models.Model):
    
    writer = models.ForeignKey(Author)
    title = models.CharField(max_length=1000)
    edition = models.CharField(max_length=1000)

Let's say I want to standardize the above two models to both call their author 'author', and their title 'title'. In terms of code, the most sensible way to do this would be to define an abstract base model as follows:

class Document(models.Model):

    class Meta:
        abstract = True
    
    author = models.ForeignKey(Author)
    title = models.CharField(max_length=1000)

class Book(Document):
    page_count = models.IntegerField()

class Magazine(Document):
    edition = models.CharField(max_length=1000)

So we just change that, and now we're all good, right?
Not so much. In order to effect this change on our database, we're going to need six migrations:
    - Schema migration to add `title` field to Books
    - Data migration to copy `book_title` to `title` for  each Book
    - Schema migration to delete `book_title` field
    - Schema migration to add `author` field to Magazines
    - Data migration to copy `writer` to `author` for each Magazine
    - Schema migration to delete `writer` field

All of these will have to happen at the same time, because all of the code changes have occurred simultaneously. If we wanted to avoid this, we would have to go through incremental code changes to our original models BEFORE we arrived at our desired setup of having an abstract base model.

While this is possible with foresight and planning, the more models that you wish to standardise, the harder a series of incremental code-database-code changes becomes.
So in the situation where we simply have to make this migration, how should we do it?

Idea 1: The Great Migration
===================

If we have several million Books and Magazines, this is going to be one slow migration. For most apps in production it would introduce an unacceptable amount of downtime. We can sidestep this issue by spinning up a second, similarly sized database, transferring our data to it, and running the migration on our database copy. 

In order to do this, we make use of Heroku pgbackups:transfer from [Heroku PG Extras](https://github.com/heroku/heroku-pg-extras/). This wonderful tool allows one to dump a Heroku database directly into a second DB, while the first database is running. The contents of the second database will exactly mirror that of the first, **when the dump was started**. Subsequent changes to the primary database will, unfortunately, not be reflected in the follower. To do this, we run: 

`heroku pgbackups:transfer <production db> <full URL of destination db> -a <production app>`

Once our database is transferred, we can proceed to carry out our schema and data migrations in isolation. A Django ORM caveat - use objects.iterator in the data migration code or your operation will become memory-bound as every single object in the queryset will be cached in memory.

If your migrations are hitting different, unrelated tables you can run them concurrently(!!!) on a per-app basis. Since the migrations may take a long time, we use the heroku run:detached command to avoid the process being killed if our shell connection to Heroku dies. So, for example we could launch:
heroku run:detached python myapp/manage.py migrate books -a <migration app> 
heroku run:detached python myapp/manage.py migrate magazines - a <migration app>
These migrations will run concurrently on the Books and Magazines tables, assuming these are in the separate apps books and magazines.

In an ideal world, once the migrations were complete we would simply promote the new database to our application's However, the savvy readers among you will have recognised an obvious problem with this strategy.
 