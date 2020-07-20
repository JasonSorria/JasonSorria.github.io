---
layout: post
title: How to change or add system font
date: 2019-12-25
tags: linux    
---

### Why need to change system font  

For me, it not only beautify my system, which make my system seem as a very nice tool, but some font like AwareSome font can support icon font. Maybe many guise do not know what is icon font and how to use it. Icon font is a kind of font which uses the minimum memory size to display a icon like that:

![](/images/posts/font/show.png)

### Let's start     

- **1 create a fonts directory:**

    `$ cd /usr/share/fonts && mkdir new-fonts && cd new-fonts`

- **2 download fonts style on baidu or google, i recommend [nerd fonts](https://www.nerdfonts.com/), and unzip it**

- **3 add your TTF file into this new-fonts directory**
    
    `$ mv xxx*.ttf .`

- **4 load the fonts:**

    `$ fc-cache -fv (yum install fontconfig)`

- **5 list all fonts on linux:**
    
    `$ fc-list`

### Q&A

> Q:

> A:
