---
layout: post
title:      "Rails session does not persist?"
date:       2020-11-14 16:16:50 +0000
permalink:  rails_session_does_not_persist
---


Off course not if your project structure it's the same as my one.
If `rails new` it's used with `--api` flag then it won't store the session hash after a refresh.
It gave me a hard time because I was checking with `byebug` in my create session method: 
 ```
 def create
    @user = User.find_by(email: params[:email])
    if @user && @user.authenticate(params[:password])
      session[:user_id] = @user.id
      render json: {
        status: :created,
        logged_in: true,
        user: @user
      }
    else
      render json: {status: 401}
    end
      byebug
  end
```
In the `byebug` console my `session[:user_id]` had the right value, but, it was not persisted.
After hours spent on google and stackoverflow I found the solution.
In my config/application.rb file, inside the Application class I added the following: 
```
config.middleware.use ActionDispatch::Cookies
config.middleware.use ActionDispatch::Session::CookieStore, key: '_backend_chat_app'
```

That sorted the problem, and after a refresh, my session hash is still there.

