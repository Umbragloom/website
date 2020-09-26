---
title: Setting Up Vim
date: 2020-09-26T12:16:20-04:00 
draft: false
tags:
 - Linux
 - Tutorial
 - Vim
---

# Vim needs no introduction. 
----

Well that's not entirely true, it probably does if you have never heard of it.
`vim` or Vi IMproved, is a well known port of the vi editor created by Bill
Joy, that was created by Bram Moolenaar. `vim` was designed as a more improved
text editor over the original vi, with a heavy influence on the use of the
keyboard over the mouse, and pre-installed movement commands, or custom macros,
to traverse the document you are creating or editing. For more detailed
information, including the history of Vim, please go to the home page at [vim.org/](https://www.vim.org/)

# Installing Vim 
----

To install `vim` consult your Linux distributions wiki. A few of the popular
ways are below:

For Arch based systems:
```bash
$ sudo pacman -S vim
```
For Unbuntu based systems:
```bash
$ sudo apt install vim
```
For Debian based systems:
```bash
$ apt-get install vim
```

# Basic layout
----

When you first start vim via `$ vim` you are greeted with the following screen:

{{<image src="/images/vim_screen.png" position="center" >}}

Pretty simple design and can get you buy if your need to edit some files, but
i'm going to edit it up a little and make it cleaner, and nicer to use a little
later. But first lets go though some of the most basic commands that should be
learned. 

One of the best things to do if you have never used vim before is to run `$
vimtutor` in your preferred terminal. This is a very nice introduction to the
standard movements utilized in Vim. A few of the really important ones are:

1. The hjkl keys - this is the standard movement keys for getting around in the
   file you are using. `h` moves left, `j` moves down, `k` moves up, `l` moves right. 

2. Exiting - use `:q` to exit, `:q!` to force a quit, and `:wq` to write the file and exit vim. 

3. When in normal mode (the standard) mode, you can utilize a number in front
   of the action you would like to do, such as `2j` moves 2 down, `32k` moves 32
   characters up, etc. This can also be utilized for other commands. 

4. In normal mode the `x` button will delete a single character at the cursor, `dw`
   will delete from the cursor to the end of the word, including the space,
   `d$`
   from the cursor to the end of the line, `dd` to delete a whole line. 

5. What about if you did something and want to undo it? simply pressing `u` in
   normal mode will do that for you.

6. What about if you want to just update a word: `cw` and type the  correct word then press `<ESC>`. 

7. Pressing `i` will put you into INSERT mode. 

These are just some of the basic commands that can be handled from within vim,
`vimtutor` as well as the documentation can aid you in learning and figuring out
other macros and commands. 

# Setting up customization.
----

Vim utilizes a configuration file, the vimrc. This vimrc can be utilized
globally, or at a user level by utilizing a `.vimrc` file in your home
directory. 

Here you can choose which settings you would like to add. A few of the options
I utilize are below:

```vim
"set line numbers to both relative and number.
set number relativenumber

"set file stats
set ruler

" spacing and whitespace things
set wrap
set textwidth=79
set tabstop=4
set shiftwidth=4
set softtabstop=4
set autoindent
set nofoldenable
```

You can also set custom key macros as well. A few of the ones that are useful
to me are:

```vim

" set jk to esc
inoremap jk <esc> 
vnoremap jk <esc> 

"disable arrow keys
map <up> <nop>
map <down> <nop>
map <left> <nop>
map <right> <nop>

" Auto Close tags. Adds the start and close tags and centers the cursor in the
" center.
inoremap ( ()<Left>
inoremap { {}<Left>
inoremap [ []<Left>
```

Then you can utilize Plugins to get other features. I use a program called
[Vundle](https://github.com/VundleVim/Vundle.vim) to install plugins. To
install Vundle follow the README found on the github, thtough that link. 

Some of the plugins I utilize are 

1. (NERDtree)[https://github.com/preservim/nerdtree] - A custom file system
   explorer for Vim. Need to also use (Vim-devicons){https://github.com/ryanoasis/vim-devicons} to get working file system icons. 
2. (Onedark)[https://github.com/joshdick/onedark.vim] - A Dark colorscheme for
   Vim/Neovim. Sometimes I use (Gruvbox)[https://github.com/morhetz/gruvbox].
3. (vimrainbow)[https://github.com/frazrepo/vim-rainbow] - Colorizes your
   paranthesis, brackets, and squierlies to make them easier to distinguish. 


These are just a few of the plugins I utilize. After installing and setting
everything up my vim now looks like below: 

{{<image src="/images/vim_custom.png" position="center" >}}

# $ sudo exit
----

This was a VERY simple introduction to vim. There are a plethora of resources
online for learning how to utilize, configure and customize vim. a few
suggestions that i have used are :

1. The vim documentation.
2. the following youtubers / channels: (Luke Smith)[https://www.youtube.com/channel/UC2eYFnH61tmytImy1mTYvhA], (ThePrimeagen)[https://www.youtube.com/channel/UC8ENHE5xdFSwx71u3fDH5Xw], and (Thoughtbot)[https://www.youtube.com/user/ThoughtbotVideo]
3. (VIM Adventures)[https://vim-adventures.com/] - a really fun interactive
   game, created to easily teach vim movements, while playing an RPG style
   game. 

If you would like to see my vimrc and other dotfiles please feel free to go to
my (Github)[https://github.com/Mathie-Josh/Arch_laptop/]. I need to update my
README, but the files are all there!

I hope you enjoy the wonderful and majestic world that is vim!

----

