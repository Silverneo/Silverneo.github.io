---
layout: post
title: "OCaml setting up notes"
description: "Setting up OCaml compiler in my cygwin environment"
category: notes 
tags: [OCaml, cygwin, setting up]
---
{% include JB/setup %}

A short note on my OCaml installation steps.

1. Install cygwin from cygwin.org. (Omit this step as I did it hundreds times already!)
2. Download [OCaml](http://caml.inria.fr/ocaml/release.en.html), I chose the source tarball package.
3. Unpacked the tarball by typing `tar -xzf ocaml-xxx.tar.gz`.
4. Go to the source file folder,  type the following command one after another.
    $ ./configure  
    $ make world  
    $ make opt  
    $ make opt.opt  
    $ make install  
    $ make clean  
5. Type `which ocaml` to check whether successfully installing the OCaml

For details, please refer to the install file inside the source file.
