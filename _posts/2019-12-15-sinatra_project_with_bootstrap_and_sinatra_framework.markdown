---
layout: post
title:      "Sinatra Project with Bootstrap and Sinatra Framework"
date:       2019-12-15 23:07:22 +0000
permalink:  sinatra_project_with_bootstrap_and_sinatra_framework
---

This project requires us to make a Web Application using Model, View, Controller(MVC) along with Create, Read, Update, and Delete(CRUD) actions as well as has_many and belongs_to relationships to build this simple Content Management System(CMS). 

## I. The Reason To Approach For GameMems

These two weeks were Sinatra Project week. I had a blur idea back on the break week before the project, which I was thinking toward making a project over pets record. However, I found it may not be as useful since most pet owners I know would not really keep track of their pet record unless it is in a serious condition. Therefore, I ended up making something that I am also really  interested in and might be more useful and that is a Web App for Game Collections. I did think about making anime version instead but since I already worked on that topic in my CLI project, I just want to work on something different.

As a game lover like me that never get to keep track of the games I've play, which I kind of regret  because I sometimes wants to go back and play those game again, but the only thing I remember is the content of the game and not their names. So there comes the idea of making my Web Application call Game Memories(GameMems).

## II. Project Structure
```
├── app 
│   ├── controllers
│       └── application_controller.rb
│   ├── models
│   └── views
├── config
│   └── database.yml
│   └── environment.rb
├── db  
├── config.ru 
├── Gemfile
├── Rakefile 
```
This is the structure of the MVC that are all in app file and the in my config file, I had to add `database.yml` so that I am be able to add tables and migrate in terminal. And all my migrate tables are in db file, where it'll create schema after I run it
```
rake db:migrate
```

and here's my Gemfile:

```
gem 'sinatra'
gem 'activerecord', require: 'active_record'
gem 'sinatra-activerecord', require: 'sinatra/activerecord'
gem 'sqlite3'
gem 'rake'
gem 'require_all'
gem 'pry'
gem 'shotgun'
gem 'bcrypt'
gem 'thin' # A thin and fast web server
gem 'sinatra-flash'
```

`sinatra-flash` is the bonus which is a very new thing to me, and interestingly enough that I learned it does have a default error message while I also have validation added. I only put one default message to the project, the rest are customized. 

During working with sinatra flash, I did face a problem with uniqueness validation. 
since I previously had my game model with
```
validates :name, uniqueness: true
``` 
along with the whatever default message:
```
flash[:error] = game.errors.full_messages.join
```
This actually brought to a problem where different user cannot add the same game name even in their own page, so I had to use scope and rearrange the way of saying the validates is unique only within that one user with:
```
validates_uniqueness_of :name, scope: :user_id
```

And it worked!! Now, different users can have the same game name in their list. 

## III. Working With Bootstrap

I chose to use bootstrap over CSS because I did have my hand on it from a Udemy course that I took before the bootcamp although I only got to a point where it was mostly just working with layouts. So I found working with bootstrap can be really fun. And It Is!

Bootstrap is a Front-End Framework that make all the designing process very easy, it has very modern layouts for us to choose from and we also can add some css part in it. It is a very useful tool to web-developers. 

### My Views With Bootstrap

I have learned that layout.erb will display the designing part in every views, but that isn't really what I wanted since "NOT" all my views have exact same layouts. Therefore, I had to put bootstrap separately in all my views. However, since all my views will have a Navbar, which is a very common use for webpages, I decided to put my Navbar along with the header into layout.erb to make it looks more DRY. 

As I learned how `<%= yield%>` work, well... I am very impress. It will automatically put all the contents in views right in it so it'll display all the pages with just one erb file. However, when I was working putting this part in yield:
```
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">

    <!-- bootstrap -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css">
    <!-- font awesome -->
    <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.11.2/css/all.css">

    <title></title>
</head>
```
I faced another problem. Because all my pages have their own title, and title always have to be inside of the head tag, so I had to have `<%= @title ? @title : "default message" %>` in it to show every pages with it's appropriate title. And yes, other than bootstrap, I also used font awesome to make it looks more user friendly (maybe just what I believe), I also learned that from the same course in Udemy.  

## IV. To Conclude....

I really have a lot of fun working with this project. Although I will be adding more stuff in it (in my own time), this project so far is to get familiar with working with Sinatra and database. I actually do have a lot more contents in mind to add, but with the time frame of the project week, I didn't think I could get through all of them so I just put some basic work that meet the requirements. 

I wish you all that are working on or going to work on this project will enjoy everything you do just like me :) 

here's my repo [link](https://github.com/pkanGitHub/GameMems) if you want to check it out! It is very basic, but it will probably be fun to play around other people's app~ 

Thanks for reading it, I hope you will have a greate day! 



