---
layout: post
title: How to change keyboard binding
date: 2019-12-28
tags: linux   
---

### Introduction

I guest that you may get bored with your traditional keyboard binding and many usually key are not at these positions in which you can convenient to touch. Today i will share a powerful and easy-to-use application named xmodmap who is a part of family of Xorg and supports permanent modify your traditional keyboard binding, so you should install some dependence of Xorg. 

### Steps

**1 download:**

`$ sudo pacman -S xorg`

**2 show your recent keybord layouts:**

`$ xmodmap`

![](/images/posts/keyborad/1.png)

**3 show id of your of all keybord layouts:**

`$ xev` when you press any keyboard you can see its id

![](/images/posts/keyborad/2.png) 

**4 input your layouts into .xmodmap:**

`$ xmodmap -pke > ~/.xmodmap && vim .xmodmap`

**5 change key you want:**

I recommend to change the Esc and CapLock because you will usually use key Esc when you edit your articles but the headache is the key Esc is far from your finger, which make you uncomfortable touch it.

Change their contents behind the id and input 'clear lock' into header of file and 'add lock = Cap_Lock'.

This is my .xmodmap file and only change key Esc and key CapLoack.

```vim
clear lock

keycode   8 =
keycode   9 = Caps_Lock NoSymbol Caps_Lock
keycode  10 = 1 exclam 1 exclam
keycode  11 = 2 at 2 at
keycode  12 = 3 numbersign 3 numbersign
keycode  13 = 4 dollar 4 dollar
keycode  14 = 5 percent 5 percent
keycode  15 = 6 asciicircum 6 asciicircum
keycode  16 = 7 ampersand 7 ampersand
keycode  17 = 8 asterisk 8 asterisk
keycode  18 = 9 parenleft 9 parenleft
keycode  19 = 0 parenright 0 parenright
keycode  20 = minus underscore minus underscore
keycode  21 = equal plus equal plus
keycode  22 = BackSpace BackSpace BackSpace BackSpace NoSymbol NoSymbol Terminate_Server
keycode  23 = Tab ISO_Left_Tab Tab ISO_Left_Tab
keycode  24 = q Q q Q
keycode  25 = w W w W
keycode  26 = e E e E
keycode  27 = r R r R
keycode  28 = t T t T
keycode  29 = y Y y Y
keycode  30 = u U u U
keycode  31 = i I i I
keycode  32 = o O o O
keycode  33 = p P p P
keycode  34 = bracketleft braceleft bracketleft braceleft
keycode  35 = bracketright braceright bracketright braceright
keycode  36 = Return NoSymbol Return
keycode  37 = Control_L NoSymbol Control_L
keycode  38 = a A a A
keycode  39 = s S s S
keycode  40 = d D d D
keycode  41 = f F f F
keycode  42 = g G g G
keycode  43 = h H h H
keycode  44 = j J j J
keycode  45 = k K k K
keycode  46 = l L l L
keycode  47 = semicolon colon semicolon colon
keycode  48 = apostrophe quotedbl apostrophe quotedbl
keycode  49 = grave asciitilde grave asciitilde
keycode  50 = Shift_L NoSymbol Shift_L
keycode  51 = backslash bar backslash bar
keycode  52 = z Z z Z
keycode  53 = x X x X
keycode  54 = c C c C
keycode  55 = v V v V
```
    
**6 save config:**

`$ xmodmap ~/.xmodmap`

### Q&A

>Q: Why it will come to become the old form each when i startup my Manjaro linux ?

>A: If i3-wm is your desktop application, it is a common thing you only need add `xmodmap ~/.xmodmap` in your Linux shell and auto execute it when you start up your system. And there is a other thing that when you plug your physical keyboard you must need execute `xmodmap ~/.xmodmap`  again.
