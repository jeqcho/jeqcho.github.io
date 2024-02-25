---
id: 77
title: 'Locked out of my own website'
date: '2021-12-14T00:26:18+08:00'
author: jeqcho
layout: single
guid: 'https://chojeq.com/?p=77'
permalink: /locked-out-of-my-own-website/
categories:
    - Chojeq.com
tags:
    - chojeq
    - freehostia
    - Wordpress
---

I am thoroughly impressed by the security features of my website. I’ve been locked out from posting my first blog on my journey of cultivating a weekly writing habit. Currently, I am using a VPN to post this blog. So how did this happen?

Me, being a forgetful and clumsy human, failed 3 login attempts to my WordPress page with password-based login (in my defense, this shows that my passwords are strong against profiling attacks). On my 4th attempt, Chojeq greeted me with a 412 Error, and advised me (shouted at me, if I am the admin), to change the mod\_security rules if I am not an attacker. A subsequent refresh renders the login page unreachable due to Chojeq *ignoring* my connection (not rejecting, what a passive-aggressive strategy).

![](https://lh3.googleusercontent.com/zEE-NpeqvPKhqOHXR62ErE64dfayvuu5uVxZSr1AiUQ53IBAl5gDrZsn0m0TzUXPvXcz6K1u4GV74JtSNQPhFPnAxNkrX4u5CHDOMYpSMTwbuFaJEFFDkWG-EbZMX_rfzn9XNvEW=s768)
Pinging up the other subdomains of my website (for example constellation.chojeq.com) shows that all of my subdomains ignore my connection, and are not specific to the WordPress login page. Fortunately, using [an external service](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.isitdownrightnow.com/chojeq.com.html%26amp;sa%3DD%26amp;source%3Deditors%26amp;ust%3D1639416079551000%26amp;usg%3DAOvVaw1zKUYCHSipajsSp-7dfAof&sa=D&source=docs&ust=1639416079557000&usg=AOvVaw0Wf7xp4kV5zsbL5JgXwkGy) shows that my website is still accessible by everyone else. Somehow, my website identified me as an attacker, so I need to try to clear that identity.

I am not a network/server expert, so I attempted clearing cookies, cache, and Chrome’s hard reload, which obviously didn’t work. Another possibility is Chojeq identified me by IP. Because Chojeq ignored me because of my failed login on WordPress, I suspected that it was a wordpress security feature. However, scuffling through WordPress built-in antispam and a plugin’s (Titan antispam) firewall settings yield no results. The plugin’s login attack logs are empty and the list of blacklisted IPs are not mine but from 2020. Deactivating the plugin doesn’t help either. Inspecting the database for any security IP lists also yields no results.

Online results suggest that it has to do with server security instead. Then it turns out that someone in 2014 faced a similar issue (his server mistook him as a rogue admin who posted offensive content, but he was just posting in Spanish) on stack overflow. I took the people’s advice, but applying an exception to .htaccess to overwrite ModSecurity failed, and further research shows that this doesn’t seem to work anymore in 2007. Also, [this post](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttp://forum.freehostia.com/viewtopic.php?f%253D4%2526t%253D65652%26amp;sa%3DD%26amp;source%3Deditors%26amp;ust%3D1639416256727000%26amp;usg%3DAOvVaw1n0uIPv60CMJM13SetMx93&sa=D&source=docs&ust=1639416256732000&usg=AOvVaw3GP8-GrvNY_3FSu1bGxqPp) shows that directly modifying ModSecurity is unavailable for the free plan I’m on.

The only option I have right now is to use a VPN. It turns out that my password is stored as plaintext in FreeHostia’s panel (which is outrageously an insecure practice, but I’m grateful as it allows me to post this tonight to wordpress). I will keep trying to fix this and whitelist my IP, but this might be a sign to switch away from FreeHostia.

**Update:** Turns out the lockout is timed. I can finally login using this IP address in roughly 24 hours later. Perhaps WordPress locks me out for a certain period of time but has trouble displaying this on the login screen and thus ignored the connection because it is unable to do so (my WP configuration is buggy and I sometimes encounter phantom “fatal” errors, though my website still stands). Or it is not a bug but a feature to give a cold-shoulder to people who nags about the wrong things (in this case the login password).