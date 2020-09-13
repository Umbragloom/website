---
title: "Installing Termux"
date: 2020-09-10T18:20:23-04:00
draft: false
tags: [Termux, Linux, Android]
---

# Installing Termux

* * * 
Today I would like to go through how I Installed Termux on my Android phone,
how I edited the app, what applications I use it for, why I installed it, and what I have learned.

First **What is** ***Termux*** you might ask? Pulled directly form the main
website [https://www.termux.com](https://termux.com/ "Termux Main Website"):

> ***Termux*** is an Android terminal emulator and Linux environment app that
> works directly with no rooting or setup required. A minimal base system is
> installed automatically - additional packages are available using the APT
> package manager.

That seems like a lot of information to take in at once. Let's break that down
further:

1. Android Terminal Emulator: This is a computer program {or in this case
a android app} that emulates a text terminal on our android phone.
2. Text Terminal:  Also just called a terminal or system console is a standard
serial computer interface for text entry and display. The system console is
a text terminal used to operate a computer. One of the main uses and
applications utilized in a terminal is the Shell, also known as a command-line
interpreter. The shell is used type out commands and execute them.
3. Linux Environment: This is simply a "Linux Like" environment that is
installed on your android phone via the Termux application. You can run normal
terminal commands as well as applications that are made to run in the terminal,
such as [Weechat](https://weechat.org/),
[ncmpcpp](https://wiki.archlinux.org/index.php/Ncmpcpp), or
[tmux](https://github.com/tmux/tmux/wiki).  It is not a linux subsystem, but
simply a package ecosystem.

# How do you install Termux?
----

There are two ways you can install Termux:
1. Through the Google Play Apps Store.
2. Through the F-Droid App - The Free Open Source Android App Repository.

The option you choose is entirely up to your preference. The F-Droid versions
add-on apps (Styling, API, Widget, Float, Boot, and Tasker) are free but are
not maintained by Frederick Fornwall, the author and main maintainer. Where as
the Google Play version's add-on apps are small costs to purchase (about $6.00 USD for all
of them I believe) and is maintained by Frederick and the money goes to helping him continue
his work. I choose the Google Play Store version as I wanted to support the
project.

# Instillation Steps:
----

1. Download the App from the [Play Store](https://play.google.com/store/apps/details?id=com.termux) Or from the [F-droid App](https://f-droid.org/packages/com.termux).
2. Open the app on your phone once it is done installing. The app will install
   the base system itself. 
3. Once this is finished you are greeted by the Termux welcome screen. I would recommend reading
   through the wiki,  there is **A LOT** of great information that
   can help you if you ever get lost. Termux uses the package manager `pkg` to
   install different applications or packages. `pkg` is used by a majority of
   Debian based Linux distributions ,or Distros,(such as Ubuntu, Linux Mint and
   Zorin OS) use pkg as standard.{{<image src="/images/Welcome_Screen.jpeg" position="center" >}}

4. Termux is now installed and ready to use. I would suggest running `pkg update` and accept the upgrade. This will make sure your system is completely up to date.

# Now to make it look better and run some stuff!
----

Now you can install a plethora of packages. You can peruse the full list
[here](https://github.com/termux/termux-packages/tree/master/packages). Some of
the apps I Installed were: 
1. `vim` - One of the best terminal based text editors around.
2. `git` - for managing git repos, also use it to push my Termux files to github
   to keep them in one place. (This is not really needed as Termux has a built
   in backup utility that saves a zip file of everything in the termux
   folder, but I am learning how to properly use git, so it helps.)
3. `zsh` - a new command-line interpreter that offers improvements over Bash. (with the oh-my-zsh framework and the powerlevel10k theme.)
4. `WeeChat` - a IRC (Internet Relay Chat) client. Other alternatives are
   [irrsi](https://irssi.org/) or [epic](http://www.epicsol.org/) among some of
   the top used ones.
5. `Tmux` - A terminal multiplexer. It allows you to switch between programs that
   you run in a session that you can detach and reattach on a different
   terminal. See the documentation at the link provided above. 
6. `OpenSSH` - Secure Shell tool for remote connection.

The easiest way to download a package is to run `pkg install "packagename"`. 

After installing the packages you want you can configure the apps further
(Please read the documentation for the package you would like to customize.)
For example I configured my .vimrc to include the
[Vundle](https://github.com/VundleVim/Vundle.vim) plugin manager.

{{<image src="/images/Termux_vim.jpg" position="center" >}}

You might notice that there are some extra rows of keys above my keyboard (such as the arrow keys, PGUP
and HOME buttons.) These are not 100% necessary, but I prefer having them.
Follow
[this](https://wiki.termux.com/wiki/Touch_Keyboard#:~:text=Extra%20Keys%20Row,Q%20or%20Volume%20Up%2BK.) link to see how to set it up.

> Quick summary copy the code block from the Wiki and paste it into a `termux.properties` file in the `~/.termux/` folder (the ~ refers back to the users `home` directory.) then tun the `termux-reload-settings` from the command line to refresh Termux and ashow the additional keys. 

After this I set up a new shell, zsh, with the [Oh-my-zsh](https://ohmyz.sh/) framework and the [powerlevel10k](https://github.com/romkatv/powerlevel10k) theme. You can
follow the git repo instillation guides for both of these for how to properly
install and configure them. After installing, customizing and restarting
Termux, it now looks like this:

{{<image src="/images/Screenshot_Termux.jpg" position="center" >}}

I used the screen capture tool `neofetch` to get the OS Printout info and the
ascii art image, that I tied to an alias `ps`, to make it easier to execute.

# Why did I install Termux?
-----

I installed Termux as a way to continue learning the Linux command line, and
understanding the packages that can be used. A majority of everything I have
installed on my laptop (BTW I use Arch...sorry that's over used..) I have
installed on my Termux application. One nice thing I can do is use my phone to
SSH into some other machine if I need to do something quickly, or ssh tunnel
into one of my VPS's running Tmux. There are a lot of options I can continue to
use the app for and will most likely write up more things about it.

# $ sudo exit
-----

Before I close out, here are a few projects on github that I personally would suggest you potentially look into related to Termux (I havent tryed any of these, but plan on looking into them):

1. [atlio](https://github.com/YadominJinta/atilo) - A termux program to install
   a few minimal linux distors inside termux.
2. [TermuxArch](https://github.com/SDRausty/TermuxArch) allows you to attempt
   to install an Arch Linux inside of the Termux environment. 
3. [Nethunter-in-Termux](https://github.com/Hax4us/Nethunter-In-Termux)
   - install Kali nethunter in Termux, WITHOUT root. 

&nbsp;
&nbsp;
&nbsp;

-----

