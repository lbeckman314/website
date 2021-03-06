---
title: code
---

<div class="container">
    {% for code in site.code %}
    <div class="fixed pointer featured">
        <a class="code-src" href="{{code.src}}"></a>
        <img class="center" src="/assets/images/{{code.img}}">
        <p class="code-title">{{code.name}}</p>
            <div class="type-container">
            {% for type in code.type %}
                <span class="code-type {{type}}">{{type}}</span>
            {% endfor %}
            </div>
        <p class="code">{{code.content}}</p>
    </div>
    {% endfor %}
</div>

# Interactive Demos

Feel free to try out some programs in an interactive sandbox. Click on any of the examples below to give them a spin.

{% include demonic.html command='prime 10101' %}

<hr />

<h1 id="security">make checksums, not war</h1>

[My GPG Keys](https://pgp.mit.edu/pks/lookup?op=vindex&search=0x144F39B7AC1CC079):

signer = `liam beckman ("I only want to live in peace, plant potatoes, and dream!" -Tove Jansson) <lbeckman314@gmail.com>`

key id = `AC1CC079`

key fingerprint = `2C81 8D24 2991 72E8 57D1  B235 144F 39B7 AC1C C079`


```shell
#-------------------------------#
# RECEIVE GPG KEYS
#-------------------------------#

gpg --keyserver pgp.mit.edu --recv-keys AC1CC079

#-------------------------------#
# RECEIVE SHA256SUMS
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

gpg --delete-key AC1CC079
```
