---
title: Personal Website with Hugo and Netlify!
date: 2021-07-28T12:19:00-0400
draft: false
description: "Setting up Hugo, hosting to Github, deploying with Netlify and Netlify CMS."
tags:
 - Linux
 - Tutorial
 - WebDev
---

# Static websites are amazing!
----

Building your own website, and hosting it is easier than ever nowadays,
especially with things such as WIX, WordPress and Squarespace. But i wanted
a bit more of a personal technological feel behind it to justify having one.

# Why do this?
----

There are a lot of reasons to host your own website. My reasons are below:

1. I wanted somewhere I could post what ever I wanted. 

2. I wanted to learn a little of both the front end and backend development
   that went into WebDev and website management. 

3. It looks go to potential employers, as well being able to act as a simple
   portfolio. 

# How to get started.
----

RESEARCH is your best friend. Look into YouTube videos, Read the documentation
from the [Hugo](gohugo.io/getting-started/quick-start) and research other
peoples code bases if they have them available to you.

# So where do I even begin??
----

## First Steps!
The first thing to do once you've done your research is to install Hugo. For my
example I will be doing this on Linux. There are a plethora of resources on how
to handle this if your on Mac or Windows. 

From your terminal make sure whatever system you are using has git installed or
Homebrew if you go that route. For me as I'm using Arch Linux, i can just
install Hugo directly from the Arch Linux community repository by using the
following command in my terminal.

```bash
$ sudo pacman -Syu hugo
```
Then you should verify the install with the following:

```bash
$ hugo version
```

Your Command line should show the version number of Hugo if it was installed
correctly. If it does congrats you have the Hugo Framework installed.

Next steps are to create a new site! 

```bash
hugo new site "sitename"
```

The above command will create a new Hugo site in a folder called "Sitename", you can replace sitename with your desired site name.

Congrats you have the start of a website, but its going to be pretty bland
starting off. 

## Make it ***STAND OUT***

From here you should add a theme. There are HUNDREDS of themes
you can install. the best place to go is, you guessed it, the [Hugo
Themes](themes.gohugo.io) page. 

For my website I went with the Amazing [Terminal
Theme](themes.gohugo.io/themes/hugo-theme-terminal/) from panr on
[Github](github.com/panr/hugo-theme-terminal).

This is where Git comes in, you need to clone the theme into your websites
folder. For the Terminal Theme, panr recommends using a git submodule, which
allows you to use the updates made to the repo. To do this type the following
into your terminal:

```bash
$ cd sitename #to move into your hugo root folder.
$ git submodule add https://github.com/panr/hugo-theme-terminal.git
themes/terminal
```

This will install all information you need to utilize the theme on your
website, in a dedicated theme folder within your root folder of your website. 

From here just follow the documentation to set up the theme and your ready to
go and start making posts. 

# Post and post and post!!

Now its time to start making some glorious, glorious content! You can manually
create content files for example typing `content/<CATAGORY>/<FILE>/<FORMAT>`
and provide metadata in them, however I would recommend the `new` command to do
a few things for you (like add title and date):

```bash
hugo new posts/"your-posts-title"
```

This will create a new .md file for you to edit. Hugo utilizes markdown syntex
for your website pages. 




