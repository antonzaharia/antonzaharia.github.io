---
layout: post
title:      "Rails Project - RGadgets"
date:       2020-06-30 15:25:36 -0400
permalink:  rails_project_-_rgadgets
---


### Rails project was the one that I was most excited about. I knew it will be awesome because it will  accumulate most off the concepts learned by know in this journey.

I've started on draw.io creating the database and writing down in a notepad all the associations needed. This is what I end up with:

(https://prnt.sc/t9bzmq)

It scared me at the begining, realizing that it will need a lot of work. 

### Creating `Users`, `Addresses` and `SessionsController`

The models I started with was `User` and `Address`. It was easy and it didn't create any problems as I really love the signup idea and always that was my favourite part.

The place I spent more time was on implementing the new form for the `Addresses` as it was a nested resource of the `Users`, I completely forgot that the `form_for` requires 2 instances. `(@user, @address)` 

### Adding `Items`, `Categories`, `Models` and `Colors`
This was the moment when I understood the reason why a DRY code is very important. It can be hard even for myself to find the line of code I need when the code is "WET".
(Models and Colors I associted with Items with a `has_many` relation.  `Item blongs_to :color`)

First Refactor.

### Adding `Carts` and `CartItems`
This was the moment of `has_many through:` relation.
A `Cart` has many items through `cart_items`.
While I was building up the form for the new cart I realised that an `Item` should HAVE MANY colors and models.

Second Refactor

I had to drop my items, models, and colors tables down and modify them as they should be.

### Implementing the GitHub signup.

Firstly I tried with Facebook but my Visual Code Studio won't let me start the rails server with `thin start --ssl`.
After 3 or 4 hours on facebook develepment website and trying almost everything I found on Google about the errors I was getting I decided to use GitHub.

GitHub was not requiring ssl so my server was back on. But I faced a strange issue:

In my `request.env['omniauth.auth']` my email was `nil` and my `User` model was not valid without an email.

 I sorted the problem by creating a new class method in my `User` model: `create_with_omniauth`
 
```
def self.create_with_omniauth(auth)
        create! do |user|
          user.uid = auth['uid']
          if auth['info']
             user.name = auth['info']['name'] || "No Name on GitHub"
             user.email = auth['info']['email'] || "Add your email here."
             user.password = auth['info']['email'] || "BasicPassword"
          end
        end
   end
```
This method helped me a lot. If the GitHub email was not found in `auth['info']` hash it is saving it as "Add your email here", so the user can add it anytime accessing `edit_user_address_path` from the user show page.

### Adding Bootstrap
This was a fun part where I was only adding classes in my views. It was fun but also I was feeling like that my views became much harder to read.
Websites need a bit of styling as they are a big part of the user experience.

Third Refactor.

## Here am I, happy with my new "skills" and proud of my first Ruby on Rails project.
 



