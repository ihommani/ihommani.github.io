Title: Ranger
Date: 2014-04-13 22:10
Category: tools
Tags: file manager
Slug: ranger
lanf: en
Author: ihommmani
Summary: Why ranger is worth to try, and it offers a good alternative to classic file managers ?


Ranger is a file manager where thing can get fast...blazingly fast.   
I trully think you should give it a try. At least to test another paradigm of file manager.   
So, **is Ranger a true alternative to classic file managers **?  
As always, the right response would be "It depends.".
Ranger has strong requirements. And the step could be too high for some people.

#Ranger ?
Put in few words, Ranger is a **file manager with curses interface**. 
As a file manager, it allows you to do the basic CRUD operations on your file system but also operations such as setting rights on files, excute or previewing files...
Unlike classic FM all is fast since you control it through your keyboard and shortcuts and not your mouse.
Ranger step out of your way so you can focus on the important things.  
Another interisting fact is how far you can tweak it to closely match your needs.


# Interface
Ranger relies on curses interface to display informations.  
This is the first step to address for someone used to GUI.  
No more shinny feature. All you have is a bunch of columns and lines.
Yet the all thing is **clear enough to navigate through**.   I will also add that it provides more informations than a classic FM since you not only see the content of the current directory but also the content of the directory you point. Avoiding you to enter a directory to check its content.   
The advantage of not relying on graphic server are numerous.   


* Ranger is usable in the console   
Pretty cool for sysadmins

* You save a plenty of resources  
For instance on my 3Go RAM computer (pretty low in the time writting this article) the memory print wouldn't go over 0.5%. So it is for the CPU comsumption.


![interface]({filename}/images/ranger1.png "ranger's interface")

*Navigation is by default made through the central column, although you can change the parent directory from this column*


# The tip are the tips of your fingers
The second steps to address is to accept the fact **you won't need a mouse**.
Concerning the mouse I think there is some kind of addiction. We can't (or don't want to) see alternative, either when mouse is not the best mean.   
Don't get me wrong, mouse is useful for many usecases and without alternative in some case(Gaming, web browsing).   
But there is a better alternative in the case of file manager, and mouse is no match for the speed of the keyboard...in the case you 
master the type touching i.e typing without watching your keyboard.   
That is the second part of the step. **You have to invest yourself in mastering your keyboardi**. 
And believe me in a month or two you'll thank me.

# Installation
Ranger requires python 2.6 or higher. 
Although you can install it with a tarball provided in the official [site](http://ranger.nongnu.org/download.html, "ranger download"), it is adviced to use the package manager of your distribution.
In any case installation should be easy.

# Parametrisation
One cool aspect about ranger is the way you can tweak it.   
Almost every aspect is configurable. Keybinding, colors, applications to open/preview files...
Ranger relies on four files for the configuration:


* rifle.conf 


* commands.py


* rc.conf


* scope.sh

They have to be in the directory *~/.config/ranger* .  
To easily bootstrap these files we can take advantage of the *copy-config* option: 
```
$ ranger --copy-option all
```
This has for effect to bootstrap your configuration directory with default configuration files.

## Rifle.conf
Ranger uses a program named rifle to open/execute files.  
To configure rifle you've got to modify **rifle.conf** .  
This file describes to rifle what application to use when you want to open or execute a file. 
It describes with a specific syntax how to reconize file (by name, by extension, by regex...) and how to handle it.   

## Commands
Ranger commands are defined through the file **commands.py**.  
This python file contains classes, each one representing a command.   
To interface with ranger the class has to define at least some specific methods.  
All is well explained in the comment header of the file.

Not only you can modify some behavior, you also can create new commands.
Here's a simple hello_world command:  
I want the hello_world [args] command to display "Hello World [args]" on the screen.

```
class hello_world(Command):
    """:hello_world [args]

    Display hello world on console
    """
    def execute(self):
        if self.args:
            self.fm.notify("Hello world %s" % self.args)
        else:
            self.fm.notify("Hello world!")
```

Here's the explanation.  
Each class must extends the Command class.  
Then it has to interface to ranger by defining the *execute* metod.   
Inside this method we use the *fm* object which contains most information about ranger.  
Now we can use our new command inside ranger by typing *:hello_world foo*   


It also exists others methods. I let you **read the fantastic header** to understand the purpose of each one.

## rc.conf
The purpose of this file is to define the ranger's startup settings.  
It is where you'll find most of the ranger's setting.   
To know about the setting you can modify, the manuel is a good starting point. 
It is where you also specify keybinding. By default, **ranger comes with a vim keybinding**, but it's up to you if you want to keep it or change it.

This file is also a treasure of information and you should read it at least once, to discover all the setting and shortcut you've got.   
Ranger is powerfull only if we know how to take advantage of it.

*E.g, not only you got keybinding to navigate, you also have keybinding to sort files and directories, launch unix commands such as **df**, filter files...* 

**Note**: *To not forget it you can easily switch from Ranger to your terminal with **S**, and go back to Ranger by exiting the same terminal.*


## scope.sh
Like rifle but used to preview files.  
Very useful, instead of opening files you check through the preview if it is the file you are looking for. Also works for pdf and images.

![interface]({filename}/images/ranger2.png "ranger's preview 1")

*Example of a text file preview*

![interface]({filename}/images/ranger3.png "ranger's preview 2")
*Example of an image preview. Note that this ascii preview rely on my geek taste, but you can perfectly preview a 'normal' aspect. Just read the scope.sh header*

## Theming
You can of course change the style of ranger by creating an existing theme or creating a new one.  
The good thing is that creating a new one is easy thanks to inheritance.
You just have to create a *your_theme.py* in the colorsheme directory and define inside a class *Scheme* inheriting from Default class.   

It can be as small as this:

```
class Scheme(Default):
    progress_bar_color = green
    def use(self, context):
        fg, bg, attr = Default.use(self, context)

        if context.directory and not context.marked and not context.link:
            fg = green

        if context.in_titlebar and context.hostname:
            fg = red if context.bad else blue

        return fg, bg, attr
```

You then specify the theme you want in the rc.conf file by putting the following line in your rc.conf  
```
set colorscheme your_theme
```

# Plugins
To add features to Ranger without modifying the core of it, ranger support plugins. I don't include them in the scope of this article. However it is well documented and nice example are to be found under **/usr/share/doc/ranger** directory.

# The downsides
While i'm praising keyboard over the mouse, I have to confess that the drag and drop is a feature we do not have with ranger.   
It's the major ranger's drawback of i can see.

# Conclusion
I have used ranger for years.  
Ranger is different from other file manager. It gives a different experience while managing your files.  
Not only it is light and fast, it also stick to your needs to an extent no other file managers can match.  
Last but not least, a word from our beloved comrade.  

![Texas]({filename}/images/texas_ranger.jpg "Texas ranger")
