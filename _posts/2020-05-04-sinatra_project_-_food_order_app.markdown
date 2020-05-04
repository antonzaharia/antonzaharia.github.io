---
layout: post
title:      "Sinatra Project - Food Order App"
date:       2020-05-04 14:17:30 -0400
permalink:  sinatra_project_-_food_order_app
---


### I was inspired to start this project by my second job. I work as a delivery driver for a company that have this kind of web app.
### I have to be honest. This is my second try as the first app I wrote, I did it without thinking about all the attributes I will need for every model.

I had 4 models firstly. `User`, `Restaurant`, `Order`, and `Item`(Items being the restaurant dishes). Then I realised that I need another object: `OrderItem`, so different instances of orders can use many items. Then I realised that I need an `restaurant_id` in the `Item` model, because items `belongs_to` a restaurant. And then I wanted to add more info about the items, so I created the `description` attribute. And then I realised there is no price for the items. After that I needed a `quantity` attribute for `OrderItem` model.

## What I am trying to say is that my migration folder was full. 
It was really easy to forget about an attribute of a model and I needed to check again all the migration files. That was not very comfortable and it was taking time.
### So I decided to `destroy` all my tables and recreate them as they should be.

### I started again with everything I needed and everything went as planed.

After all the logic was there and everything was working as it should:

User: signup, login, logout, create new order, cancel order ( available only for a period of time), see all previous orders.

Restaurant: signup, login, logout, create new item, edit item, delete item, see all restaurant orders.

### I have implemented a couple of errors like:

```
if User.find_by(:email => @user.email)
      @error = "This email already in use."
      erb :'/users/signup'
    else
```

This won't let a user to sign in if the email the entered is already in the database.
Or
```
if params["restaurant"]["email"].empty? || params["restaurant"]["password"].empty?
      @error = "Email and password cannot be blank."
      erb :'/restaurants/login'
    elsif
```
This won't let a "Restaurant Partener" to login if any of the input is empty.

This will prevent my app to crash.

### Finally I added Bootstrap.

That was the easy part where it was only about how the site will look, but..
While I was checking every single `.erb` file to add the classes from boostrap I have noticed a couple of things that I either build wrong or simply forgot to write.
So adding the bootstrap was kind of refactoring my code and make it ready to submit.

## This project was as challenging as I expected but the proccess of building a website from scratch is amazing.

### So here am I, proud of my first webb app and excited about what I will learn next.
