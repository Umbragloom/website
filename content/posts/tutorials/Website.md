---
title: Personal Website with Hugo and Netlify!
date: 2021-07-28T12:19:00-0400
draft: false
description: "Setting up Hugo, hosting to Github/Gitlab, deploying with Netlify and Netlify CMS."
tags:
 - Linux
 - Tutorial
 - WebDev
---

# Static websites are amazing!
----

Building your own website, and hosting it is easier than ever nowadays.
Especially with things such as WIX, WordPress and Squarespace. But I wanted
a bit more of a personal technological feel behind it to justify having one.

# Why do this?
----

There are a lot of reasons to host your own website. My reasons are below:

1. I wanted somewhere I could post what ever I wanted. 

2. I wanted to learn a little of both the frontend and backend development
   that went into WebDev and website management. 

3. It looks good to potential employers, as well being able to act as a simple
   portfolio for projects, and things you are passionate about. 

# How to get started.
----

RESEARCH is your best friend. Look into YouTube videos, Read the documentation
from the [Hugo](https://gohugo.io/getting-started/quick-start) and research other
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

The above command will create a new Hugo site in a folder called "Sitename", you can 
replace sitename with your desired site name.

Congrats you have the start of a website, but its going to be pretty bland
starting off. 

## Make it ***STAND OUT***

From here you should add a theme. There are HUNDREDS of themes
you can install. the best place to go is, you guessed it, the [Hugo
Themes](https://themes.gohugo.io) page. 

For my website I went with the Amazing [Terminal
Theme](themes.gohugo.io/themes/hugo-theme-terminal/) from panr on
[Github](https://github.com/panr/hugo-theme-terminal).

This is where Git comes in, you need to clone the theme into your websites
folder. For the Terminal Theme, panr recommends using a git submodule (as does the Hugo dev team), which
allows you to use the updates made to the repo, without causing any harm to the master branch of the repository once you start making changes to it. 
To do this type the following into your terminal:

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
$ hugo new posts/"your-posts-title"
```

This will create a new .md file for you to edit. Hugo utilizes markdown syntex
for your websites content. Below would be the example of what will be in your new post that you can open in any viewer:

```vim
---
title: "Your Posts Title"
date: 2019-03-26T08:47:11+01:00
draft: true
---
```

This will make whatever you put in "Your Posts Title" the title of your first post, then 
display the date of the post. The next line `draft: True` is important, this sets the post 
as a draft that will not be posted to your site, until it is ready. 

# Check it out!
---

So after youve set up your website, chose a theme that you enjoy (or made your own), and posted your 
first piece of content you can start the hugo server and view the local copy of your website in any browser! 
Type the following into your command line:

```bash
$ hugo server -D
```
Your terminal will output something similar to the below:

```bash
$ ▶ hugo server -D

                   | EN
+------------------+----+
  Pages            | 10
  Paginator pages  |  0
  Non-page files   |  0
  Static files     |  3
  Processed images |  0
  Aliases          |  1
  Sitemaps         |  1
  Cleaned          |  0

Total in 11 ms
Watching for changes in /Users/bep/quickstart/{content,data,layouts,static,themes}
Watching for config changes in /Users/bep/quickstart/config.toml
Environment: "development"
Serving pages from memory
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
Press Ctrl+C to stop
```

This will load the hugo server for you,and all you need to do is navigate to http://localhost:1313/ 
and view your website!! The -D option loads any drafts that you have so you can view them before posting!

From here you can continue to configure your theme by updated the themes `config.taml` file. Here you 
can set a base url if you have a domain ready, replace the title for your webpage, as well as many other 
options!

---

But ***"Wait!"*** you say, ***"My website isn't online now is it?"*** The answer to that is yes, your correct 
its not online, and canont be accessed on the web. This is where Netlify and Github come in handy!

# Git Commit!

So you've made your site, configured it to your hearts content, and seen what it will look like from your browser, now your ready to 
get yourself setup online. For this we will transition our website's root folder into a Git folder! On your commandline `cd` ,or change directory, 
into the root folder of your website (Should be something like: `~username/home/mywebsite/` if you made it in your home folder)
then run the following commands:

```bash
$ git init
```
This will intialize the folder as a git repository waiting to be pushed to Github/Gitlab. Go to your Github/Gitlab create a new repo, and copy the supplied `git remote add` and `git push` commans from the `...or push an existing repository from the command line` section, then commit the changes to the staging area and commit them to Github:

```bash
$ git add . #this adds all files in the root folder to the staging area.
$ git commit -m "Your commit message here" #This is the commit message that you should use to keep track of changes you have made to your git folder, this is useful if you are working in groups.
```
Then push the local Git repo to your repository on Github/Gitlab:

```bash
$ git remote add origin https://your-github's-repository-address.git
$ git push -u origin master
```
Congrats you have now begun the process of keeping all data on Github/Gitlab for version control!

# Netlify to the rescue!

Next steps are to deploy your website on ***Netlify***. Head over to [Netlify](https://netlify.com) and create an account. You can also use your Github login details if you feel like that would make it easier. Once your logged in you'll see an option `New site from Git:` click this and you will be asked to choose your git provider, Either Github ot GitLab, Choose which ever site you used. From here youll be asked to install Netlify on your personal GitHub/GitLab account, Choose the repository where your website is then youll be asked to verify your build settings. For this set the build command as `hugo` and what directory you need to publish, for us this is the `public` directory where all our content is stored. After this is confirmed click the `Deply site` button at the bottom of the page.

Your website will not be correctly displayed if you proceed to the URL shown on the in the site overview since it does not match the `baseUrl` setting value in the `config.toml` file. Therefore, click on the `Deploy settings` in the site overview. Then select the `Site details` under the `General` tab. In the `Site details` tab, click on the `Change site name:` button, this will cause a pop up to show up, from here set it to whatever your `baseUrl` setting was, be it a domain name if you have one. 

#***CONGRATUALTIONS***

You now have your own personal website, that is manual updated once you make new posts to your website on whatever device your Git folder is in! Now on to setting up netlifies CMS so you can edit, update and push content remotely from netlify's CMS system!





