

##Meet APISpark##

##Context##
### The web is resources ###
Most of us think the internet as a huge  set of html pages. Some of us think the internet as a huge set of resources.
I do think so and to understand what an API is, you ought to think that way.
Web pages are usually made of Html which is a semantic language your browser unserstand and hence can display.
For instance the current web page.
But Html is not the only media type you can find on the internet. There are many [more](https://en.wikipedia.org/wiki/Mime_type ""). 
Atom, rss, Pdf, zip are among the most famous.
Let's say we have a server we put on the internet to serve various types of data such as text, video and sound. By serving, we can understand sharing.
To share we have to give access to those **resources**. Notice I purposely used the word resources. No matter if we consider sound, video or anything else. They are all resources. Even an Html page is a resource.


### Why would I give access to resources ? ###
As an individual you surely want to share all those html files composing your web site. 
In that case your clients are web browser. They request your html pages to display it to the final user. 
But as an enterprise or if you run a business, you would give access to valuable resources or allow other aplications to **consume** your resources. This time, clients are other web applications.
A good example are web applications which compare prices between airlines. Airlines better have to give access to such information otherwise they would miss business oppurtunities offered by the comparators.
Not only you want to give access to resources, you also want to **receive content**.
Flickr, Facebook and co would literally be useless if they wouldn't be able to receive content. They also need to later give access to this content.
As we can see, giving access to resources is far form being useless.


Guess who gives me access to this beautiful map ?:
![Map of NYC](http://maps.googleapis.com/maps/api/staticmap?center=Brooklyn+Bridge,New+York,NY&zoom=12&size=600x300&maptype=roadmap&markers=color:blue%7Clabel:S%7C40.702147,-74.015794&markers=color:green%7Clabel:G%7C40.711614,-74.012318&markers=color:red%7Clabel:C%7C40.718217,-73.998284&sensor=false "New York")


### How can I give access to resources ? ###

All these informations have to be consumed or received through an interaction point usually called interface.
The general meaning of an interface is at the same time a boundary and a point of interaction between two sides.
We can also think the interface as a contract defining rules of interaction.
In the web domain we give it the name of [webAPI](https://en.wikipedia.org/wiki/Web_API "WebAPI").
We call those two sides the client side and the server side. Basicaly, the server side responds to request emitted by the client.
None of them needs to know about each other. Only the interface allow them to interact.

As you may already understand, when you want to give access and receive resources, you have to define a webAPI.
In concrete terms, entry points are URL through which the server will receive the client's HTTP requests.

What you do when receiving the request is completely up to you. But you have to respect the contract you specified through your API documentation.

Should we give access to all of it? Of course not. You decide what you want to expose, what you want to receive and who you want to interact with.

To sum up, to expose resources we mainly have two things to do. 
1. Define an adress where you can contact the server.
2. Define and describe an interface to interact with my resources at the previous address.

To meet the first point's requirement you need to rent an IP adress to a hosting platform or to your ISP.
The second point is usually made with [webFramework](https://en.wikipedia.org/wiki/Web_framework "Web framework") which provides the necessary tools to define yout API.

As we will see, APISpark helps you to satisfy both at the same time.


## APISPark ## 
###What is it?###
APISpark is a [PaaS](http://en.wikipedia.org/wiki/Platform_as_a_service "Platform As a Service") which aims to provides you with a turnkey solution for creating API.
It provides answer to the API hosting and resource accesibility.
In comparaison with usual solution (webFramework + hosting plateform) you do not have to code anything.
All you do is focusing on the important thing: The data model and the way you want to expose it.
Still, we can't say that APISpark is easy enough for a rookie, and you still have to understand the API concept to trully master the tool.
###How it works###
APISparks relies on three type of entities. 
1. The **Custom API**
2. The **EntityStore**
3. The **FileStore**

![APISpark entities](http://apispark.org/images/tutorials/tutorial1-15.png "entities")


The last two entities are also called dataStores. 
Model: EntityStore
View: FileStore


The Custom API is the API you want to publish. It is backed up by EntityStore**s** and FileStore**s**.
I stressed the s because nothing prevents you 


Association between an 

### Why APISpark ###
###Use case###
Meal
### Is it fine ?###
Blunders

On the one hand we do not have to code. But on the other hand we do have to understand some concept to be able to use it. 
In my opinion the target is not well define. We may say that this kind of tool is too much easy for a programmer who won't find the tunability he has with webFramework. But we can also way, it's to difficult for a person with no technical background.

## Conclusion ##
The promesses made by APISpark are obviously tremendous and apealing.
You can build your own API in  a matter of minutes and APISpark takes care of everything.
Yet, the project is still young and some blunders are to be reported. The beta version is available since December 2013, not so long ago at the time writting this article.
With your contribution, by mentioning these problems to the APISpark team, you would speed up the fix up and enhance the overall quality of the tool.
A tool I'm sure we will hear again soon enough.

