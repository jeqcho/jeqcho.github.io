---
id: 59
title: 'Behind the scenes: Chojeq.com'
date: '2021-08-13T17:33:46+08:00'
author: jeqcho
layout: single
guid: 'https://chojeq.com/?p=59'
permalink: /behind-the-scenes-chojeq-com/
categories:
    - 'Behind the Scenes'
tags:
    - behind-the-scenes
---

In the winter (laughing in Malaysian weather) of 2017, I started my self-coaching coding journey by reading “Javascript for dummies” from [PDF Drive](https://www.pdfdrive.com/). Things escalated quickly as I discovered how to make things move by manipulating the CSS styles of a HTML element dynamically via Javascript. I begin to start making some games using this idea, one of which is [C](https://archive.chojeq.com/games/game.php)[–](https://archive.chojeq.com/games/game.php)[Pong (archived)](https://archive.chojeq.com/games/game.php). At that time, these projects are static: they only require a browser like Google Chrome to run, so it was possible making and playing them locally without any server.

In a few weeks, I moved on to the “PHP” section of the book, (turns out that the book had 7 volumes, each touching an aspect of web development), and I was guided to install an Apache server on my Windows machine, using [XAMPP](https://www.apachefriends.org/index.html). With it, I can run PHP code on my local machine and host a local MySQL database. It was fun making a content management system (CMS) from scratch, and I made one for flirters.

Until then the only place to visit my projects was my computer and the only people who knew about it was my family. It wasn’t long until I thought of showing my projects out of my family, and to the world. A quick online search culminated in me making an account on [freehostia.com](https://www.freehostia.com/) (I can’t remember whether the book pointed me to this website as well), which I still use to host chojeq.com. Their free plan is good enough for me:

- 250MB storage
- 10MB MySQL database
- 3 E-mail accounts
- 6GB monthly traffic
- FTP support
- SSL: Let’s Encrypt support
- Custom domain and subdomains (more on this later)

So far so good. I use [FileZilla](https://filezilla-project.org/) (free) to transfer my files to FreeHostia via FTP, though sometimes I use their online control panel for small edits. The only downside is that you will only have a single MySQL database, so all of my projects share the same database. I know this is an unacceptable practice in the industry, but hey it is a free plan.

After some time, I decided to give my website a more personal identity. I’ve been using some edgy (but free) domain names from FreeHostia, so I decided to register my own domain. I chose [Google Domains](https://domains.google/) (I am a big fan of Google), and initially wanted to name my site nasikochi.com. Thankfully, my parent who I reached out for the domain registration fees talked sense into me and I settled with chojeq.com. 3 years later and I’m grateful I chose chojeq.com. Google Domain sells a typical domain for RM50/year, which is a good price for such a good investment. There might be cheaper alternatives out there, including the popular [namecheap.com](https://www.namecheap.com/) and [godaddy.com](https://my.godaddy.com/), but they have a lot of chargeable add-ons (that you might or might not need), while Google is straightforward and powerful with a single standard price. Go for Google Domains if you want a peace of mind.

The good thing about FreeHostia is that it supports [Let’s Encrypt](https://letsencrypt.org/) (free SSL), so my website can communicate securely in https, which makes my visitors (and me) feel safe browsing my website (I don’t have store any sensitive information here, but having the padlock logo is very reassuring). Another bonus is email hosting (send/receive/forward/anti-spam). People can contact me via hi@chojeq.com because of that. (I still can’t get over that [Google Workspace](https://workspace.google.com/) doesn’t have a free plan for personal use).

Sometimes I host my projects on subdomains. It began with [red-buttons.chojeq.com](https://red-buttons.chojeq.com/) because it is a very destructive webpage and I don’t want it to bring the entire chojeq.com down with it in terms of SEO and resources. FreeHostia is good here because it supports up to 15 subdomains.

Some of my projects are hosted on [Heroku](https://www.heroku.com/) or [pythonanywhere](https://www.pythonanywhere.com/), while those that require installation are linked to their GitHub repository. I will write more about these projects in separate blog posts.

In August 2021, I decided to revamp my website as it had outgrown it’s 3 years of hard-coding. I have learnt not to reinvent the wheel but to use the technology available to reach my goals. Previously, my homepage was hardcoded with a template from [Colorlib](https://colorlib.com/). Now that I wanted to blog as well, I realised that [wordpress.org](https://wordpress.org/) is [different](https://www.wpbeginner.com/beginners-guide/self-hosted-wordpress-org-vs-free-wordpress-com-infograph/) from [wordpress.com](https://wordpress.com/). The WordPress software itself is free and open-source under the GNU Public License. I proceeded to install WordPress in my server (Freehostia has support as well). Now WordPress handles my blogging infrastructure, without any commercial branding on the client side. The branding only happens if you use wordpress.com to build and host your wordpress.org project.

How much does of all of these cost? RM50/year for chojeq.com, and the rest is free thanks to the open-source community, and the existence of the concept of free tiers. You can even do all of this for free if you use a free (but edgy) domain.

Side note: try [GitHub Pages](https://pages.github.com/) too if your site is all static (only HTML, CSS, JS, no PHP or Python).