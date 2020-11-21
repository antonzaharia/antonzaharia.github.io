---
layout: post
title:      "Why I used Rails sessions insted of JWT"
date:       2020-11-21 16:00:40 +0000
permalink:  why_i_used_rails_sessions_insted_of_jwt
---

After doing my research about JWT tokens, I decided to enable Rails sessions and start using them for my authentication system.
 What changed my mind was an article I found on cryto.net.

> If an attacker manages to inject a malicious script into your front end (which is vulnerable to XSS), then they can use that script to make HTTP requests to your server (directly from the user’s browser) and your precious httpOnly cookie (containing the user’s valid session ID) will be attached to every request so the server will service them without suspecting anything.

How I enabled sessions if my app was using an api Rails app you can find out here:
https://antonzaharia.github.io/rails_session_does_not_persist

