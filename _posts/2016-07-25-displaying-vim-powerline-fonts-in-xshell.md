---
title: Displaying Vim Powerline Fonts in Xshell
categories:
  - Tools
tags:
  - Vim
  - SSH
  - Linux
---
Xshell and Vim have long been my favorite combination for working on remote Linux machines over SSH connections. Today I had to reconfigure my settings on a new Linux Server. Downloading my backed up Vim plugins and configuration files were no problem. However the custom symbols for the Vim-Airline plugin were not displaying correctly.

![Wrong powerline symbols]({{ site.url }}/images/2016-07-25-wrong_L.jpg) ![Wrong powerline symbols]({{ site.url }}/images/2016-07-25-wrong_R.jpg)

Normally this required installing the patched fonts from [https://github.com/powerline/fonts](https://github.com/powerline/fonts) but today this method couldn't do the trick. It couldn't have been Xshell's issue since a recent [blog post from Xshell](http://blog.netsarang.com/93/super-charging-terminal-with-powerline/) confirmed that the SSH client now supports Powerline fonts out of the box. After several attempts to reinstall the patched fonts without yielding any luck, a peek into the `.viminfo` file under my home directory gave me the answer. The default encoding method of Vim on that machine was `latin1` and not `UTF-8`. Since my vimrc never tried to set the encoding, the symbols provided by Vim-Airline could never be correctly parsed. A simple addition to my vimrc file would do the trick.

#### ~/.vim/vimrc

```VimL
" Set encoding displayed
set encoding=utf-8

" Set encoding written to file
set fileencoding=utf-8
```

Now my Vim could display the special symbols with no problem.

![Correct powerline symbols]({{ site.url }}/images/2016-07-25-correct_L.jpg) ![Correct powerline symbols]({{ site.url }}/images/2016-07-25-correct_R.jpg)
