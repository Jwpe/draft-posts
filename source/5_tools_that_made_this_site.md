Having a personal website is pretty useful. Not only does it provide a constant source of entertainment and tinkering - there's always something not *quite* right about the implementation or the pixel height of the navigation bar - it also acts as a platform to put forward ideas. After a couple of months of having no fixed online abode (most of which was spent loitering on Twitter), I decided that it was time to reestablish myself. This was particularly prompted by two pieces of good fortune: firstly, that the Peruvian government has seen fit to offer two-letter domain names; and secondly, that jw.pe was mercifully available. 

So here's my new site. I thought it best to inaugurate it by discussing some of the tools that were used in its creation. Hopefully these will prove useful to others in future projects! Note: if you're an experienced dev, you can probably skip straight to 4 and 5, unless you want an amusing overview of the basics.

##1. [Django](https://www.djangoproject.com/)

This may be a little obvious, since I'm primarily a Python developer, but this site runs on Django, 'the web framework for perfectionists with deadlines'. If you haven't encountered Django before, I suggest reading the documentation, particularly the [tutorial guide to building your first app](https://docs.djangoproject.com/en/1.5/intro/tutorial01/). There are also many other good starter guides that can be found by Googling ['Django -unchained -reinhardt'](http://lmgtfy.com/?q=django+-unchained+-reinhardt).

If you're already familiar with Python, you can also check out the source of this site, which is on my [GitHub](https://github.com/Jwpe). The curse of every Django developer is to feel obliged to roll their own blog implementation - indeed, it could be considered something of an inauguration. Fortunately, this isn't my first blog, so I was able to reuse a lot of code. Some might argue that Django is too heavyweight for a simple blog site, but I find it well-suited for a couple of reasons:

+ Class-based views (the merit of which is a discussion for another day) allow very easy provision of lists of posts or articles, complete with pagination.
+ The Django admin interface works fairly well as a stand-alone CMS.

##2. [Heroku](https://www.heroku.com/)

Hold on to your hats, people, because this site is not running on a Linux box in a dusty corner of my room. I am, in fact, making use of what we in the business call a [PaaS or Platform as a Service](http://memeimages.com/wp-content/uploads/2012/07/neil-degrasse-tyson-watch-out-badass-meme.jpeg). The PaaS in question is Heroku. Honestly, most people reading this probably know what Heroku is. For the uninitiated, Heroku is a magical place where your entire website can live in 'the cloud'. It is amazing because:

+ You can deploy your code very easily via git.
+ It has literally tens of of pluggable services you can add to your application (think monitoring tools, databases, asynchronous task/worker services), many of which are free.
+ Several very talented Python engineers work there.
+ It [scales really well](http://news.rapgenius.com/James-somers-herokus-ugly-secret-lyrics)!

##3. [GitHub](https://github.com/)

In the whispered legends of the past, one hears tales of a dark time when only one Developer could work on a single piece of code simultaneously. When a crashed PC could mean hours, days or even YEARS of lost work. Then came Source Control, and it was good. 
But the Developer grew greedy. "What," said the Developer, "if I wish to make some changes to my code at home, which is inconveniently located in a forest with no internet access, and then add those changes to a centralized repository at a later time?" Frowns all round. 
Suddenly, a dazzling light struck the Developer, accompanied the melodious croon of harps and angelic voices. The Developer saw, squinting, the silhouette of an [outspoken Finnish man](http://www.theregister.co.uk/2013/06/11/linus_torvalds_threatens_developers_pets/) approaching, bearing a distributed version control system. It was Git.

GitHub has fast become the standard location for storing git repositories. If you want to host code, GitHub is the place to do it - public repositories are free, and private repos for business/super-secret projects aren't expensive. It also has an amazing interface. Nowadays, a programmer's GitHub account is like a second CV. Have they made a bunch of apps for fun? Do they contribute to open source projects? A quick glance at GitHub will tell you these things and more.

##4. [Draft](https://draftin.com/)

Right now, I'm writing this post on Draft. It's autosaved. It's version controlled. It's formatted in Markdown, and I can export it as HTML. In short, it's fantastic. Draft is the writing medium I've been wanting to exist, without knowing it, for some time. It's like Google Drive, if Google Drive were optimised for writing content. Did I mention that Draft syncs with Google Drive?

For the non-technical reader, if I had to recommend one tool from the five on my list it would be this. Draft - thanks to its simple, no-nonsense interface and excellent functionality - has significantly reduced the mental barrier to writing that normally stands between me and content.

![Background colour, font typeface, colour and size are fully customizable on Draft](https://jwpevans.s3.amazonaws.com/images/draft.png)


##5. [Foundation](http://foundation.zurb.com/)

Last, but certainly not least, Foundation. I am predominantly a back-end developer, by which I mean that I do not have a flair for design. Foundation, a CSS/HTML framework from the good people at ZURB, allows the design-challenged like myself to create a responsive website which is relatively easy on the eye. The simple, intuitive grid framework greatly aids layout, and the framework comes with excellent built-ins such as a navigation bar. 

If you do decide to incorporate Foundation into a site's front-end development, I thoroughly recommend getting hold of the [SCSS version](http://foundation.zurb.com/docs/sass.html) of the framework. Learning a little [SCSS](http://sass-lang.com/) will vastly improve your CSS development experience thanks to benefits like easy nesting, variable assignment and inheritance.

*** 

Hopefully this post has given you some ideas for where to get started if you want to roll your own blog site from scratch, on the cheap! For those with a site of their own, what technologies did you find invaluable in its creation? Let me know in the comments. 