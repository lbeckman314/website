---
title: code
---

<div class="rainbow-box">
    <p>All of my projects are <a href="https://opensource.org/osd-annotated">open-source</a> and <a href="https://www.gnu.org/philosophy/free-sw.en.html">free</a>. Source code can be found on <a href="https://gitlab.com/lbeckman314/">gitlab</a>, <a href="https://github.com/lbeckman314">github</a>, or <a href="https://git.liambeckman.com">cgit</a>. Contributions of any kind are always welcome!</p>
</div>

<div class="container">
    <div class="fixed pointer featured" onclick="location.href='https://convida.liambeckman.com'">
        <a href="https://convida.liambeckman.com"><img class="center" src="/assets/png/convida.png"></a>
        <a class="code-title">Convida</a>
        <a class="code-type web-app">web app</a>
        <p class="code">Conway's Game of Life implemented in Rust and WebAssembly.</p>
    </div>

    <div class="fixed pointer featured" onclick="location.href='https://github.com/removemywaste'">
        <a href="https://github.com/removemywaste"><img class="center" src="/assets/png/removemywaste.png"></a>
        <a class="code-title">RemoveMyWaste</a>
        <a class="code-type android">android</a>
        <a class="code-type web-app" id="rmw">web app</a>
        <p class="code">An application for household hazardous waste removal.</p>
    </div>

    <div class="fixed pointer featured" onclick="location.href='/code/demo/'">
        <a href="/code/demo/"><img class="center" src="/assets/png/demo.png"></a>
        <a class="code-title">demo</a>
        <a class="code-type web-app" id="demo">web app</a>
        <p class="code">A terminal emulator emulator that allows users to try out programs.</p>
    </div>

    <div class="fixed pointer featured" onclick="location.href='/code/demonic/'">
        <a href="/code/demonic/"><img class="center" src="/assets/png/demonic.png"></a>
        <a class="code-title">demonic</a>
        <a class="code-type web-app" id="demonic">web app</a>
        <p class="code">Like <a href="/code/demo">demo</a>, but more demonic!</p>
    </div>

    <div class="fixed pointer featured" onclick="location.href='https://withfeathers.liambeckman.com'">
        <img class="center" src="/assets/png/withfeathers.png">
        <a class="code-title">withfeathers *</a>
        <a class="code-type web-app">web app</a>
        <a class="code-type command-line">command line</a>
        <p class="code">Add a little Emily Dickinson to your day.</p>
    </div>
</div>

# * Interactive Demos

Feel free to try out some of my programs in an interactive sandbox. Click on any of the examples below to give them a spin.

<div class="demo-examples-container">
    <code class="demo-examples">devilish</code>
    <code class="demo-examples">matriz multiply mBig1 mBig2</code>
    <code class="demo-examples">palindrome</code>
    <code class="demo-examples">prime 10101</code>
    <code class="demo-examples">withfeathers --print</code>
    <code class="demo-examples">wyeast</code>
    <code class="demo-examples">zigzag-server</code>
</div>

<pre id="info"></pre>
<div id="terminal">
    <textarea class="terminals" tabindex="0" contentEditable="true"></textarea>
</div>
<script src="/assets/js/demo.js"></script>
<script type="text/javascript">MYLIBRARY.init(["prime 10101"]);</script>

<div id="button-container">
    <span id="duplicate-terminal">+</span>
    <div class="what-is-this">
        <a href="/code/demo">About</a>
        |
        <a href="https://github.com/lbeckman314/demo">Source Code</a>
        |
        <a href="https://liambeckman.com/code/term">Demonic</a>
    </div>
</div>

<br/>
<hr />

<h1 id="security">make checksums, not war</h1>

adapted from the "Verifying file integrity and its digital signature" section of <a href="https://www.voidlinux.org/download/#verifying-file-integrity-and-its-digital-signature">the Void Linux download page.</a> (Copyright 2018 VoidLinux contributors. Copyright 2008-2018 Juan RP and contributors.)

My GPG Keys:

signer=`liam beckman ("I only want to live in peace, plant potatoes, and dream!" -Tove Jansson) <lbeckman314@gmail.com>`

key id=`AC1CC079`

key fingerprint=`2C81 8D24 2991 72E8 57D1  B235 144F 39B7 AC1C C079`


```shell
#-------------------------------#
# RECIEVE GPG KEYS
#-------------------------------#

gpg --keyserver pgp.mit.edu --recv-keys AC1CC079

#-------------------------------#
# RECIEVE SHA256SUMS
#-------------------------------#

wget http://www.liambeckman.com/pkgs/EXAMPLE/sha256sums.txt{,.asc}
# or if you prefer curl:
# curl http://www.liambeckman.com/pkgs/EXAMPLE/sha256sums.txt{,.asc} -o sha256sums.txt -o sha256sums.txt.asc

#-------------------------------#
# VERIFY SHA256SUMS
#-------------------------------#

gpg --verify sha256sums.txt.asc

# gpg: Signature made Tue Oct 31 11:11:11 2017 PDT using RSA key ID AC1CC079
# gpg: Good signature from "liam beckman ("I only want to live in peace, plant potatoes, and dream!" -Tove Jansson) <lbeckman314@gmail.com>" [unknown]

#-------------------------------#
# VERIFY FILE INTEGRITY
#-------------------------------#

sha256sum -c sha256sums.txt 2>/dev/null | grep EXAMPLE.tar.gz

# EXAMPLE.tar.gz: OK

#-------------------------------#
# OPTIONALLY REMOVE PUBLIC KEY
#-------------------------------#

# to remove my public key from your public key ring, simply
gpg --delete-key AC1CC079
```