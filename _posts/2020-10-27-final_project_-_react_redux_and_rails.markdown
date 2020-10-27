---
layout: post
title:      "Final Project - React, Redux and Rails"
date:       2020-10-27 15:09:30 -0400
permalink:  final_project_-_react_redux_and_rails
---


#### I am finally writing my final project blog post which will include all my thoughts about Flatiron School.

Like my last project, I have built a "raffle" website, with 2 interfaces: regular user and admin.

#### Learned from the other projects I started feature after feature, be sure that the previous one is working properly and trying to write a good and reusable code and not just a "working" feature.

Rails database has tables like: `users`, `posts`, `questions`, `answers`, `carts` `cart_items` and `tickets`.

### Users

There are 2 types of users: admin and regular users.  This type cannot be created from the website as I wanted only one admin. That means any new signup will `create` a new regular user and will give access to a cart, an account page, and the ability to create new tickets.

Creating `users` was the first line of code from this project. After building the signup form I was missing Rails when `session[:user_id]` was sorting out the logging in problem. Not being a safe method I used the localStorage to store the information I needed as I wanted to be focused React-Redux part. Rails authentification is implemented with `has_secure_password` at the right place.

### Posts

After users, the website needed "content".
Here I used the `React Router` to make the posts shareable following the RESTful conventions.

Every post show page contains a small form that allows a user to choose an answer to the post question and a quantity of the tickets wished to purchase.

This page requires two actions before it can add something to the cart: 
~ to be logged in (so the user can have a cart linked - obviously -)
~ to choose an answer(any answer)
After that, it passes the job to the Cart.

### Cart

Cart is the place where the tickets are being reviewed before being checked out.
The `<TicketInput />` component is loaded here the second time so if a user wants to change it to be handy.
Passing all the info to the creation of the tickets happens on pressing the Checkout button.

### Tickets

Tickets are the main thing that a user can create on this website.
Once checked out a ticket gets a number and represents the "win" or the "lost" of the post.
All the "purchased" tickets will show up on the account page of the owner user.

### Raffle

Raffle is not a database table but it represents the random way of choosing a  number.
This happens only from the Admin Dashboard.

#### Admin 

The admin is responsible for creating, editing, or deleting a post.
## Challenges
Being able to work with rails server and npm server at the same time gave me the first problem.
I sort it out by using the rails server on port 3000 starting my server with `rails server -p 3001`

A lot of code is confusing and many times I was searching for a piece of code that was in another component, so I started to keep my components as small as possible and name them as descriptive as possible.
A good example is when I created my `FormInput` component. I used it on the Signup and Login form. 
It is rendering input for and is using the details from the props to manage the right data:
```
export default function FormInput({data, handleChange, value}) {
    const makePlaceholder = data => {
        return `Enter your ${data}`
    }
    return (
        <Form.Group className="reg-form-index" name={data}>
            <Form.Control
                onChange={handleChange}
                value={value}
                name={data}
                type={data === "name" ? "text" : data}
                placeholder={makePlaceholder(data)}
            />
        </Form.Group>
    )
}
```

Trying to develop a function that needed some information that is not already present. I am trying to point to my attempts to build the cart that was iterating over some cart_items that were not built correctly as tickets were not yet implemented. My cart_items records were not hitting the database and I was trying to show them in the cart. These mistakes can give bad headaches sometimes.

## Conclusion

This project needed all the skills developed from the basics of Ruby until 'redux-thunk'. Even if I did a couple of google searches, maybe for a syntax problem or a reminder of javascript build-in function, I am happy I know what to search for.

Maybe not the best-looking website but here am I: happy of being part of the Flatiron Family and proud of my project and with the knowledge that I got so far.

## Final thoughts

After hours spent in the front on my computer, after X cups of coffee, after hundreds or maybe thousands of google searches, Flatiron School is the best thing that happened to me so far.
I am so happy I am part of it and I would never change a thing in my last 10 months.

## Thank You!


