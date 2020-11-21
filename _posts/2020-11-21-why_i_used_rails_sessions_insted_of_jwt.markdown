---
layout: post
title:      "Why I used Rails sessions insted of JWT"
date:       2020-11-21 11:00:41 -0500
permalink:  why_i_used_rails_sessions_insted_of_jwt
---

After doing my research about JWT tokens, I decided to enable Rails sessions and start using them for my authentication system.
 What changed my mind was an article I found on cryto.net:

> If an attacker manages to inject a malicious script into your front end (which is vulnerable to XSS), then they can use that script to make HTTP requests to your server (directly from the user’s browser) and your precious httpOnly cookie (containing the user’s valid session ID) will be attached to every request so the server will service them without suspecting anything.

How I enabled sessions if my app was using an api Rails app you can find out here:
[Rails sessions does not persist?](https://antonzaharia.github.io/rails_session_does_not_persist)

Creating an app that will not be used a large number of users at the same time will not have any problem handling the cookies on the server-side.

That being said, my app is ready to receive users, and they can perform the authentication parts securely.
But, no content yet. Web sockets and their implementation fill follow. 
