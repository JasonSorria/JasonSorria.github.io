---
layout: post
title: Markdown syntax and some tools
date: 2019-12-24
tags: Markdown
---


### What Markdown

Markdown is a plain text markup language that is easy to remember and write. Users can use these markup symbols to generate expressive documents at the lowest input cost: as you are reading this article. It uses simple symbols to mark different titles, split different paragraphs, bold or italics some text.

Most importantly, it can be used with vim and you only need install some vim plugins, you can browser your note on Google chrome or Firefox.  Is it not so nice?

Many product documents are also written in markdown, and are saved in the directory of the software under the filename "README.", especial Github.
　　
### Some common syntax

Title            
H1 :# Header 1            
H2 :## Header 2           
H3 :### Header 3           
H4 :#### Header 4           
H5 :##### Header 5            
H6 :###### Header 6      

>effect:

# Header 1       
## Header 2      
### Header 3     
#### Header 4    
##### Header 5   
###### Header 6  

======================================================

Url link:`[Title](URL)`.

Picture: `![Picture](/picture-path)`

>effect:

[localhost](localhost)

![](/images/posts/markdown/test.png)

======================================================

Bold :`**Bold**`.

Italics :`*Italics*`.         

Bold and italics :***bold and Italics***

>effect:

**bold**

*Italics*

***bold and Italics***

======================================================

show code : `alert('Hello World');`        
show code : ```alert('Hello World');```

>effect:

`Hello World`

```shell
this is a pice of code
```     
you can modify the syntax hightlight like shell,C/C++...

======================================================

Delect line :`~~text~~`.          

>effect:

~~text~~

======================================================

List: add *,+,- to become a new list item.

List include: need Enter+ three Space

>effect:

* item
- item
+ item

* item fater
   * item child
        * item baby
            * item cell

======================================================

Reference : > reference contents.               
Reference : >> refrence contents.               
Reference : >>> refrence contents.               
Reference : >* refrence contents.               

effect:

> refrence
>> refrence
>>> refrence
> * refrence

======================================================

Paragraph: empty line between paragraphs.           

======================================================

Line break: enter two spaces at the end of a line.

```
---
----
***
****
```
>effect:

---
----
***
****

======================================================

Most of the syntax of CSS can also be used on markdown, but different renderers render different markdown content styles. The following links contain markdown basic syntax. You can also try to write some on the following platforms.


### Some nice Markdown editor

[MaHua](http://mahua.jser.me/?utm_source=mindstore.io) online Markdown editor and not to debug.

[Markdown Plus](http://mdp.tylingsoft.com/) a powerful Markdown editor which supports to add task,emoji and flow chart.


[Cmd Markdown](https://www.zybuluo.com/cmd/?utm_source=mindstore.io) a powerful and cross-platform Markdown editor and it has released desktop client.

[Macdown](https://github.com/MacDownApp/macdown) a open source project on Github and support Mac OS.

[GitBook Editor](https://www.gitbook.com/editor?utm_source=mindstore.io) a online tool supporting multiple user to edit. it can write note easily and support all team togather to edit, espacially it remian the style of YingXiang note.

[Outlinely](http://www.glamdevelopment.com/outlinely?utm_source=mindstore.io) a Mac application which owns simple and elegant interface and easy to use, and support syntax of Markdown.

[Classeur](http://classeur.io/?utm_source=mindstore.io) easy to use and own simple and elegant interface.

[DeerResume](https://github.com/geekcompany/DeerResume?utm_source=mindstore.io) a online tool for programmer to make resume.                

### Q&A

> Q:

> A:
