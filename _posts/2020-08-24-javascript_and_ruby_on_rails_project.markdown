---
layout: post
title:      "Javascript and Ruby on Rails Project"
date:       2020-08-24 18:05:11 +0000
permalink:  javascript_and_ruby_on_rails_project
---


I have started this project with a small fear in heart as I heard from more students and professors that Javascript will be the hardest part so far.

### Backend 
I started my app by firstly creating two folders: /backend end /frontend.
In the backend folder I created a new Rials app using the `--api` flag.
Than I have generated two resources: `Top` and `Option`.
After that anytime I needed an information or a chenge on the backend I was creating an new Controller action that was completing any request.

### Frontend 
This part is the longest as all the JS file are here.
I have started with a `DOMContentLoaded` event that is making a fetch request to the Top index action to get all the tops from the database.
Creating HTML from the collected information from the database required tow Javascript classes ( same as ruby models ) `Top` and `Option`. Both classes have a static method that takes as an argument an array of instances and uses and istance method that creates the HTML which will append to the main div (tops) or to the next sibling  (option).

### Code Refactoring
After all the features was ready to use I end up with three long Javascript files. I noticed that fetch calls, methods that includes the word "vote" as well as Notice/Errors messages was repeating.
#### That was not a DRY code.
I have implemented another three Javascript classes":
#### 
Fetch. that has two static methods `simple()` ( which handels get requests that does not require a `configObj` )and a `complex()` method that handels most of my fetch calls as can take as an arguments httpVerb, body, link, and a callback.
#### 
Error. that has a static method which creates the HTML and two instance methods that uses the static method and set the correct css class and the message of the error.
####
Vote. that handles the vote events and calls the appropriate Top or Option method.

### Conclusion
Creating a Javascript and Rails one page website was not as scary as I thought. Even if is not a complex website I tried to write my code in the correct way and not only a code that works.
Here am I ,happy and proud of my project.


