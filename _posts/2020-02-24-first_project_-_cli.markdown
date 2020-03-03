---
layout: post
title:      "First Project - CLI"
date:       2020-02-24 17:25:47 -0500
permalink:  first_project_-_cli
---

### After spending three hours to setup my local environment I started to think about my first project: a command line interface.
### Firstly I was thinking to create a Dictionary CLI, to scrap from dictionary.com, but I end up by creating a `Best Seller Book CLI`.

### I started by searching a nice and clear website with a top of 20 best sellers books, than watched a couple of videos to understand how to create a github repository.
### After I wrote my plan about the project base, the party started. It started with the `Scraper` class, where I load up the website with the top 20, using Nokogiri and Open- URI. After that I build the `Book` class that contains all the methods that creates a book, like `new_from_index` which takes in 4 arguments and creates new instances of the `Book` class, and all the attributes: `:title, :author, :date, :url, :price, :reviews, :description, :delivery, :pages, :sales_rank`. Also, the `Scraper` class contains a method called `create_books`, that iterates over the whole page scraped and creates a new instance of a `Book` using the `new_from_index` method mentioned earlier.
### Finally my favourite part: `CLI` class. This was the place where my program was talking back to me. I simply love that. In my call method I used the `Scraper` class to create all the list using the `Book` class and from there the user chooses what the program will do, for example: which books the want to see, 1 to 5 or maybe 15 to 20, they can change their mind, they can choose which book they would like to see more details, and finally they can end , where the program will say a polite goodbye or the can start from the first begining.
### I don't want to say that was a hard task, but it was 100% challenging.
## Here am I: happy and proud to see my first program running.

