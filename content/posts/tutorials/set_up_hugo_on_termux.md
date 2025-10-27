+++
title = "Set up Hugo on Termux"
date = 2025-10-27T13:41:05Z
author = "Josh Mathie"
authorTwitter = "" #do not include @
cover = ""
tags = ["Termux", "Hugo"]
keywords = ["Linux", "Hugo"]
description = "This post will show you how to set up Termux to allow you to creat blog posts for your Hugo Site from your Phone."
showFullContent = false
+++

# Update Hugo static Site from mobile phone?

I've been slacking on the posting front to this blog, and I believe thats because if I wanted to work on this more, i'd have to sit infront of my PC and write up something and test it all from the commamd line. Although I set up the netfly CMS I rarely ever use it as doing it through the command line is my prefered method. 

Well with Termux, which i've disscussed before, we can actually manage this
pretty easily.

# Innpuutt

So to get this to work it is quite simple if you already have a git repo made
up for your project. If not you can also set it up like yoy normal    ly would. Follow my other post [found here](https://mathiejo    sh.xyz/posts/tutorials/website/)

1. First download Termux. This should be installed from the F-Droid app. After this is downloaded and installed go ahead and update with 

``` pkg update && pkg upgrade ```

2. Then install the following : Git , Hugo and your recommended editor for me thats Vim, you should aslo male sure openssh is installed.

``` pkg install git hugo vim openssh ```

3. Once these are done and there is a public key made by ssh you should copy the contents of of your public key to add it to ssh. Im not going to go into detail on how to do this but you can easily find how online. 

4. Now clone your webaite repo from github. 

5. Once this is done you should be able to make updates to your git repo and add and edit your posts as needed. 

6. If you want to test your pages as a draft like normal just use the standard ```hugo server -D```in the root folder of your website and then navigate to ```http://localhost:1313/``` This should show your website like how you would normally see it in a browser 

# Oooh Aahhh

Now you can update your website on the go from your phone!! Just make sure if you have your website stored on multiple places make sure you ``` git pull ``` to make sure everything is updated.

For example this entire post was edited and updated from Termux on my phone!


