---
layout: my-default
title: code
---

<div class="container">


<div class="fixed" id="featured" style="border: solid 1px #d5d5d5; width: 100%; margin: 0%">
    <a href="https://www.github.com/lbeckman314/devilish"><img class="center" src="/assets/png/devilish.png"></a>
    <div class="border-code"></div>
    <p class="center">
    <a id="title" href="https://www.github.com/lbeckman314/devilish">devilish</a></p>
    <p class = "code">A shell for your evil deeds!</p>

    <ul class="code">
        <li class="code"><a href="https://liambeckman.com/pkgs/devilish/devilish.zip"><img src="/assets/svg/octicons-5.0.1/lib/svg/file-zip.svg"> zip</a></li>
        <li class="code"><a href="https://liambeckman.com/pkgs/devilish/devilish.tar.gz"><img src="/assets/svg/octicons-5.0.1/lib/svg/file-zip.svg"> tar.gz</a></li>
        <li class="code"><a href="https://github.com/lbeckman314/devilish/"><img src="/assets/svg/octicons-5.0.1/lib/svg/code.svg"> github</a> / <a href="https://git.liambeckman.com/cgit/devilish">cgit</a></li>
        <li class="code"><a href="https://liambeckman.com/pkgs/devilish/sha256sums.txt"><img src="/assets/svg/octicons-5.0.1/lib/svg/file-text.svg"> checksums</a> / <a href="https://liambeckman.com/pkgs/devilish/sha256sums.txt.asc">gpg</a></li>
    </ul>

  </div>


</div>

This is a minimalistic shell along the lines of bash or zsh. It's very evil, and can do lots of cool things!

<br />
<hr />

# Installation

<h2 class="code">0. Prerequisites</h2>

[`gcc`](https://gcc.gnu.org/) :: for compiling the shell.

[`git`](https://git-scm.com/) :: for a quick git clone.

If you are running Windows, the above utilities will be packaged in any of the following: [babun](https://babun.github.io/), [cmder](http://cmder.net/), or [Linux Subsystem for Windows](https://docs.microsoft.com/en-us/windows/wsl/install-win10). Take your pick! : )

The above utilities should be installed (or readily available) if you are running a Unix derivative (such as Linux, macOS, or any of the BSD's).

<h2 class="code">1. Quickstart</h2>

```shell
# clone the git repo
git clone https://github.com/lbeckman314/devilish

# enter directory
cd devilish

# compile
make clean
make

# run the script
./devilish
```

<br />

# Uninstallation


<h2 class="code">0. Delete the directory/folder.</h2>

```shell
rm -rfI devilish
```

<br />
<hr />

# Documentation

You will be provided with a prompt (`:`), from which you can do all sorts of shell magic!

```shell
# First off, how to exit
: exit

# I can take comments and blank lines

# I can run commands in the background
sleep 100 &
background pid is 31415

# I know standard unix commands
ls
file 1
file 2
file 3

# Control-Z will run a foreground-only session
:^Z
Entering foreground-only mode (& is now ignored)
:^Z
Exiting foreground-only mode

# neato!
```