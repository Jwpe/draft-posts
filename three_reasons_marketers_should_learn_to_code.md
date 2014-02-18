Marketing is technology. Show me a marketer who doesn't use the internet, and I will show you an anachronism. 

These days, marketers rely increasingly on web technologies to power their day-to-day activities. Entirely aside from its strength as a marketing channel, the internet provides a plethora of tools to simplify and automate the parts of a marketer's job that would otherwise be difficult or tedious. 

While for the average marketer just using these tools might be enough, the real competitive edge lies in *understanding* the technologies that underpin them. This is where coding comes in. Even small amount of familiarity with the languages that make the internet work can produce huge gains in productivity, and give a savvy marketer the ability to truly take advantage of the information at their fingertips.

Here are three examples (in order of difficulty) of how some basic programming knowledge could be practically applied to a marketer's daily tasks.

# 1. Scoping Out The Competition's SEO, And Improving Our Own 

[SEO](http://trackmaven.com/marketing-dictionary/seo/) is an important area of focus for marketers, and for good reason - bringing people to a site via organic traffic can result in solid leads. However, it's not always obvious where to start. Optimizing for search is a tricky, ever-changing beast, and can require a lot of thought. However, we can get a good idea of what best practices are by checking out competitors' or thought leaders' sites, and applying some knowledge of HTML and the power of modern browsers.

HTML is the skeleton of the web, describing the structure of every web page from the most visually impressive to the [monstrous](http://www.lingscars.com/). If we take a look at this skeleton, we can find a lot of interesting details that give us insight into a site's SEO strategy.

To see the bones of a site, right-click on a page and click "View Page Source" in Google Chrome and Firefox, or "View Source" in Internet Explorer. The code that you see before you is HTML. We can use our knowledge of this code to look for some important site elements, otherwise known as tags. Here are some good starting points:

[gist url="https://gist.github.com/Jwpe/8950081"]

Ultimately, thanks to improvements in search engine technology, the most powerful SEO effects come from good content. However, well-structured and well-chosen HTML can still improve the effectiveness of a page, so this knowledge is invaluable to marketers. As well as taking inspiration from the competition, we can also use it to check that our own HTML content is being delivered properly. Do our blog articles contain the right keywords? Have we got too many external links, or too few? 
Knowing about HTML lets a marketer see a web page through different eyes, and better assess its value as a driver of traffic.

# 2. Content Personalization

Generating engaging, personalized content for email campaigns can be a struggle. Online CRM tools can definitely aid with this, but with a surprisingly small amount of code we can replicate the core functionality of personalizing emails for a list of leads. For this example, we'll be using the [Python](http://www.python.org/) programming language.

[gist url="https://gist.github.com/Jwpe/8947705"]

Obviously, this is a simple demonstration of the myriad information that could be inserted into a generic email script in this manner. Additionally, this code could easily be modified to read leads in from a CSV or Excel document, or to output each generated email to an individual text file for easy copying. With a bit more work, a marketer could even send the email directly from the code - skipping an email client altogether!

It doesn't need to stop at emails, either - we could apply a similar technique for any content channel where we want to send consistent but personalized messaging to leads.


# 3. Gathering Lead Data

Qualifying leads is a crucial part of a marketer's day to day. Sending dud leads to the sales team is a waste of everyone's time and money, and more often than not results in unhappiness when the lead in question discovers that they aren't a good fit for your product, or vice versa.

For better or worse, lead qualification involves sifting through a *lot* of data. Whether it's title, company size,
vertical, or any one of hundreds of possible qualification criteria, marketers and demand generation representatives need to a) go out and find the information, and b) qualify (or not) the lead based on the resulting data.

Fortunately, some coding chops can help us automatically gather lead data from a source - say, a web page - and 
organize it into a sorted form.  By putting together what we learned about HTML in example 1, and Python in example 2, we can take advantage of the ordered structure of web pages to quickly pull a list of relevant information out of a page.


One of the major advantages of using code to gather data is that it's scalable. It doesn't matter if our web page contains information about 10 leads, or 1000 - the code will handle both in a timely fashion. The technique is also flexible. We can easily adapt our script based on the structure of the page we're looking at. 

******

When I said that I'd give you three reasons marketers should learn to code, I lied. Here's a fourth, and it outweighs the practical examples above. Learning to code brings you closer to understanding the technologies you use every day. Demystifying the processes that power these tools lets you, as a marketer, have a greater understanding of the often simple logic beneath. This in turn will allow you to imagine better, smarter ways that you can leverage the available information - and with a bit of coding knowledge, you can turn your ideas into data and solutions to problems that will leave other marketers in the dust.

# Resources

Here are a couple of useful tips for getting underway with  trying out the examples above.

## Installing Python:
- On Mac - congratulations! Python is installed by default on Mac OSX.
- On Windows - [here is a simple guide to set up Python on Windows](http://docs.python-guide.org/en/latest/starting/install/win/#installing-python-on-windows)

## How to use the command line:
- On Mac - [excellent basic command line guide](http://blog.teamtreehouse.com/introduction-to-the-mac-os-x-command-line)
- On Windows - [simple guide to the command prompt](http://www.computerhope.com/issues/chusedos.htm)

## How to use Python:
- A [free, interactive basic Python course](http://www.codecademy.com/tracks/python)