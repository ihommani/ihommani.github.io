Title: Pelican
Date: 2014-01-09 23:58
Tags: generator
Author: ihommmani
Summary: How did I choose Pelican as my static blog generator 

# Presenting Pelican

When I'm reading a blog, besides the article, i'm also interested about the technology behind it. 
At first it was just good curiosity, to keep me up to date and see what reviews were made on it.
Then I started this blog. So I had to make my choice. And a clever one i.e adapted to my needs.
This choice was guided by these simple needs: 

* My blog has to be simple to host
* The tool generating it must be easy to handle
* The communauty behind it active
* Allow internationalisation i.e multi-languages articles

When it comes to host a site, there is no simpler than pure Html. No database, no logic, only text.
For this, static site generators are great. You give markup language file in input and you get html in output. 
There are a [lot of them](http://staticsitegenerators.net/ "generators list") out there. Each with a different technology, architecture... a different flavour. To give a try to each of them would take a long time so I mainly relied on my previous first searches to filter.
Github kindly provides free hosting through [github-pages](http://pages.github.com/, gh-pages). I took this oppurtunity and follow their tutorial taking advantage on the Jekyll generator.
But I encountered Pelican in my search and finally switched to it. 

This article provides answers on why I chose Pelican and not other generator.   
**This is not a tutorial. The official tutorial is enough [documented](http://docs.getpelican.com/en/latest/ "pelican doc") for this.** 


## [Jekyll](http://jekyllrb.com/ "Jekyll")
### First encounter

Like I said, I had my first static site generator experience with Jekyll. Unlike general first experiences, this, was not painful.
Thanks to a good [tutorial](http://jekyllrb.com/docs/home/ "jekyll tuto") I had a functional blog in less than an afternoon.
Jekyll engine is based on Ruby and take advantage of the liquid templating language.
Unfortunately after the basic HelloWorld, discord begun.  
Still, Jekyll is not a bad choice and provided me with a better understanding of static site generator workflow.

### The good

* Fairly simple

* Publishing is as easy as pushing a commit. 

* Using YAML for configuration

### The bad
* *Theming system*:

In Jekyll you have to specify on each post the layout to apply on it. When constructing a blog it's clearly the same layout we want for each post.
So it obviously left me a taste of duplication. If we want to change the theme, we have to change on each post the layout metadata which can be very tedious and error prone. (may you master awk...) .

* *Internationalisation*  

Through this blog I want to write in several languages. It's not cocky at all it's just about reaching a wider audience. 
English is good for this but in my opinion it's better to show we also care about other languages. We don't only code in Java, C# or C++. We do also code in Python, Ruby, Javascript...
So let's consider languages like code languages.
Jekyll, is good to distinct categories and tag, but languages, its none. We cannot simply say that: "Look, those two articles are in fact the same. They do not share the same language, that's all".
I don't say you can't reach this, I'm just saying that it is not native in Jekyll. Someone proposed to use [category](http://www.garron.me/en/blog/jekyll-multi-language.html "blog") as a substitute to language. In my opinion it's not the good way to do it. Language is not a category. If I have category movie with a post in english and chinese I have to make my choice 
between one category "Movie" and two categories "English" and "Chinese".
What I want is one category "Movie" and a link to switch from one language to another.

* *Integration with other sites*

I put it in the drawbacks but it depends on your preference. You can say I want to choose my own analytic system or comment system. In that case Jekyll 
is Ok for you. Or you can choose to prefer to only specify throuh configuration just one identifier you were provided with (disqus, ga...) and let the engine take care of the integration for you. No copy/paste needed in templates.   

## [Pelican](http://blog.getpelican.com/ "pelican")

I knew Pelican before Jekyll but never gave it a try.
Pelican engine is built on top of Python and for this reason use the Jinja2 templating language.
It's a young project with a wide community of users and commiters.

### The good: How does it fit to my needs

* *Themes*  

Pelican had a theming system somehow different from Jekyll's one. With Pelican it's more like a Plug'n play system.
Instead of manually specifying the layout on each post, you only precise once in the config file the Theme name. 
Moreover, there are plenty of [them](http://pelicanthemes.com/ "themes") hosted by gitHub. Pelican gives you a tool to manage themes installation and uninstall with pelican-theme CLI.
If you want to change your UI, you only have to change a metadata in the configfile and boom.
To bypass the theme, there is a possibility generate custom pages besides your blog entries. You can point any Jinja2 template file with a path pointing to the file and the destination path for the generated file.

*   *Internationalisation*  

Pelican is "traduction ready". That is to say, you can bound N articles as being the same article but with a different language.
For this, you just have to add two metadatas in your post:
    
**The slug**  
    *Slug* is the link between the articles. All articles with the same slug will be considered as being the same.

**The Language**  
    It comes with *slug* and specify the link's name which will allow to switch beetween versions. An error will occur at the generation if you forget it. 

* *Integration with other sites*

Pelican's themes already embed some link to sites like Disqus or google-analitycs. You only have to specify in the config-file your identifiers. 
I think it's good idea for it does all the work for you. You don't have to copy paste anything in the layout because it's already there.
If you're not fine with those sites you still can modify the templates. (to know the path: pelican-themes -lv) 
And remember that most of metadatas you specify in the config file are variables used in the layout by Jinja.

### The bad
* *Github hosting*

Unfortunately Pelican directory structure can't be pushed directly to the gh-pages repository.   
But thanks to the tool [ghp-import](https://github.com/davisp/ghp-import "ghp-import") it very easy.


## Conclusion
What can be said from all of that ?
Jekyll and Pelican are very similar. I guess it's a constant when talking about static site generator. Differences lay in the details. 
When it comes to construct a static site, Jekyll is a good to go. The liberty it provides is clearly an asset. 
But when it comes to construct a blog, you should give a try to Pelican. From my point of view, Pelican is more adapted for this than Jekyll. 
I see Pelican as an evolution of Jekyll specially adapted to my needs.
It provides me with a better experience and a smoother workflow.

Mentionable: I haven't tried yet at the time I'm writting this article but It seems that [Ruho](http://ruhoh.com/ "ruho") could also be a good choice. 
