--
layout: post
title: How to upload or download file from remote server
date:  2020-06-02
tags: Linux
---

- **1 upload a file to your server** 

    `$ scp (-P your ssh port) your file USER@your server ip:/root/myUploadFile` 

- **2 upload a dirctorty to your server** 

    `$ scp (-P your ssh port) -r /yuor directory USER@your server ip:/root/myDirectory`   

- **download file form your sever** 

    `$ scp (-P your ssh port) USER@your server ip :/the file your want` 

- **download directory form your server** 

    `$ scp (-P your ssh port) $USER@your server ip:/the directrory you want` <++>  
