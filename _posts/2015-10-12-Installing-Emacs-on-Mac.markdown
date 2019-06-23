---
layout: post
title: Installing Emacs on Mac
---

This is my own technical notes on how to install and config Emacs on Mac OS X.
<!--more-->


<a href="http://www.emacswiki.org/emacs/EmacsForMacOS#toc14">Install Emacs</a>
<code>$ brew install --with-cocoa --srgb emacs</code>

<a href="http://cask.readthedocs.org/en/latest/guide/installation.html#package-managers">Install Cask</a>
<code>$ brew install cask</code>

<a href="http://cask.readthedocs.org/en/latest/guide/usage.html">Setup Cask</a>
1. Run <code>cask init</code> under <code>~/.emacs.d</code> directory.

2. Add the following code to the <code>~/.emacs.d/init.el</code> file.
<code>
(require 'cask "/usr/local/share/emacs/site-lisp/cask/cask.el")
(cask-initialize)
</code>

Install <a href="https://github.com/rdallasgray/pallet">Pallet</a> (package management tool on top of Cask)
<ul>
	<li>Run <code>M-x list-packages</code>, and install pallet.</li>
	<li>Run <code>M-x pallet-init</code></li>
	<li>Run <code>M-x pallet-install</code></li>
</ul>

The <code>~/.emacs.d/init.el</code> should have the following content.
<pre>
(require 'cask "/usr/local/share/emacs/site-lisp/cask/cask.el")
(cask-initialize)
(require 'pallet)
</pre>

This is the bare minimum to start using and configuring packages.