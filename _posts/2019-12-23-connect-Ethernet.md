---
layout: post
title: Using pppoe to connect network
date: 2019-12-22 
tags: linux   
---

### Introduction

When you first to install linux you may face a very tricky problem that you find your system can not connect Ethernet even if you have plugged in cable. Fortunately, you still connect Internet using WIFI. When i first install i3wm desktop application, i face many tricky problems one of them is this.

### Solution

**1 if not have this command "netctl", install it:**

`$ sudo pacman -S netctl`

**2 download pppoe(a powerful and easy-to-use application basing on ppp protocol):**
    
`$ sudo pacman  -S rp-pppoe`

**3 configurations:**
    
```shell
$ sudo cp /etc/netctl/example/pppoe /etc/netctl 
$ sudo vim /etc/netctl/pppoe
# modify "interface=enp2s0   user='1806102003'   password='032992'" at pppoe file
$ sudo ip link # to look your network cards interface.
```

**4 close the network card and show the accessible network methods:**

`$ sudo ip link set enp2s0 down && sudo netctl list`

**5 connect network by pppoe:**
    
`$ sudo netctl start pppoe`

### Q&A

>Q: why i still do not connect Ethernet?

>A: it may following some aspects: 1.you can wait a while because it will verify your PPP personal informations. 2.after you use WIFI, you also can not to connect even if you shut down your network card to connect Ethernet again. 3.check your cable.
