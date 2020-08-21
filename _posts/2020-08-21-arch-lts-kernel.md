---
layout: post
title: How to change Archlinux kernel to tls
date:  2020-08-21
tags: Linux
---

### Introduction

The LTS kernel in Arch Linux is often recommended installing if you want to make your Arch system more stable. But what is the kernel? What are the differences between the default Linux and the LTS kernels, and which one should you choose? Finally, how to install the LTS kernel in Arch Linux? All these questions are about to be answered.


### Why

The LTS (long-term support) version is advantageous if stability is your first priority. It doesn’t mean that the latest kernel, or the default kernel, is less stable, it just means that the LTS kernel won’t be updated as frequently. So, there is a smaller chance of some conflicts after you update your system. Besides, the LTS kernel doesn’t change much, so if it works fine on your system it is likely that it will keep working properly.

### How

**To install and activate the LTS kernel in Arch Linux, follow these steps:**

- **Check your what kind of kernel you have:**

    `uname -r`

- **If it does not have ‘lts’ in its name, it is not the LTS kernel, To install the LTS kernel, run this command:**

    `sudo pacman -S linux-lts linux-lts-headers`  

- **Next, you need to register the new kernel in your bootloader. For the GRUB bootloader, run this command:**

    `sudo grub-mkconfig -o /boot/grub/grub.cfg`

- **Reboot your Arch Linux** 

- **When you see grub menu, select the Advanced options. Boot with the LTS kernel from the Advanced options.**

- **If your Arch Linux can not startup GUI interface like `lightdm.service`, reinstall nvidia or amd**

    `sudo pacman -S nvidia nvidia-settings nvidia-dkms nvidia-utils`

- **Reboot**
