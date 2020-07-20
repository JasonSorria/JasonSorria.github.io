---
layout: post
title: How do i manage my ssh
date:  2020-07-20
tags: Linux
---

### Introduction

I have a number of servers I need to connect to via the secure shell (SSH), and typing in the IP address or host name by hand every time. I could use an application for that, but that's bloat. Let's instead see how we can leverage small universal tools to build an elegant solution of our own instead.

Since i have to use the terminal when using SSH anyway, i will create a command-line tool using FZF which lets us type the partial name of a host and make a selection. Here is what the end result will look like:

![](/images/posts/ssh/effect.png)

### Script1

```shell
Host Vutrl
    HostName 45.32.21.40
    User root
    Compression yes
    ForwardX11 yes

Host Alicloud
    HostName 49.235.215.98
    User root
    Compression yes
    ForwardX11 yes

Host test-server1
    HostName 192.168.3.101
    User root
    Compression yes
    ForwardX11 yes
```
Some explainations: 

`Host your-server-name` it is your custom name.

save this and name it `config` store the path `~/.ssh`.  

### Script2:

```shell
# Search the input (and SSH config file) for a given HOST and print all the
# host's settings in a tabular form to standard output. The HOST must be
# provided as a global variable to the Awk process.

BEGIN {
    n = 0  # Explicitly initialise as a number instead of empty string
}

# Skip comments
/^$/ || /^#/ {
    next
}

# A new host definition after we found our host terminates
($1 == "Host" || $1 == "Match") && did_find_host {
    exit
}

# Keep searching until we found our host
$1 == "Host" && $2 ~ HOST {
    did_find_host = 1
    next
}

# Accumulate all settings and their values for our host, ordered by their
# appearance in the input
did_find_host {
    keys[n] = $1
    values[n++] = $2
    width = max(length($1), width)  # Width of the widest key for padding
}

END {
    for (i = 0; i < n; ++i)
        printf "%-"width"s  %s\n", keys[i], values[i]
}

function max(a, b) {
    return a > b ? a : b
}

```

Some explainations:

save this and create a direactoty named `bin` storing in path `~/.ssh`.

named above scripts `host2conf.awk` and store it in path `~/.ssh/bin`.    


### Script3

```shell

#!/usr/bin/env sh

export FZF_DEFAULT_OPTS='
--height=20%
--reverse
--prompt="SSH > "
--preview="awk -v HOST={} -f ~/.ssh/bin/host2conf.awk ~/.ssh/config"'

host=$(grep '^[[:space:]]*Host[[:space:]]' ~/.ssh/config | cut -d ' ' -f 2 | fzf)
[ $? -eq 0 ] && ssh "$host"
```

Some explainations:

This scripts is a program startup file and you can name it `startup.sh` 

Run `bash ~/.ssh/startup.sh` and enjoy ssh selector! 
