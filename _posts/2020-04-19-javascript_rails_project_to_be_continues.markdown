---
layout: post
title:      "JavaScript + Rails Project"
date:       2020-04-20 02:12:49 +0000
permalink:  javascript_rails_project_to_be_continues
---


With the Rails and Javascript project, I have decided to make a application for re-homing pets. This application was only for owners to post a image, their name, age, health condition, and the owner's information. There was not a option for the other user to adopt simply because I didn't want to make this starter application too complicated while still getting used to making a first time application with Javascript frontend and Rail as an API. 

In this project, I only needed two models, a pet model and a user model with
```ruby
# user model
has_many :pets

# pet model
belongs_to :user
```
In this Project, I have decided only use one controller because this is mainly a app for pets, and while my cards will only display pet's information with just a little bit of user information with it. Which I just nested user information to the form.

## Single Page App (SPA)

This application was a little different from the Rails project because we don't use multiple html for the application, but instead with the requirement, we will be building a SPA. This was a struggle for me. I said struggle, but it's more like a confusion. I tried to look up examples what define as a SPA on the web, but a lot of them looks like it's a MPA (Multiple Page App), but they are actually SPA. Therefore defining the term SPA took me a while. I do know SPA is made with only one html file, and use DOM Event Listener to manipulate it. 

### How I learned to define them
I have learned that React was created by Facebook while finding out what is a SPA, and that is what make most of the SPA out there nowadays. However, since I am not there yet, and know nothing about React just yet. I have also learned how to define what is a SPA by looking at the Dev Tool (I used chrome), since most of the time you don't get to see the source code of the web page on the internet. So when I open up a site, by looking at their "Network" in the Dev Tool, most of the website will have multiple links, so to test it out, you simply first refresh the page while having "Network" tab open and scroll to the top of the list and tries to click on other link to see how the network react to it. If the network didn't refresh but instead it's more like keep adding onto the list, it'll be a SPA, but if it refresh the first couple item on list, then it is using multiple pages like how our Rails' App was like. 

## Fetch and AJAX

### What is AJAX? 

AJAX = Asynchronous Javascript And XML

AJAX allows web pages to be:

* Updated without reloading
* Request and receive data from a server
* Send data to a server behind the scene

And we learn to use fetches to accomplish that in our project.

All Fetches are asynchronous. So what is asynchronous, and how is it different from synchronous? 
A friend of mine was explaining in a interesting way, a way that can be easily remembered: 

With Pizza Scenario...

(trying to find out why screenshot didn't show...)
![](img/Async&Sync.png)

Okay! So the main difference is with asynchronous, while you wait for the pizza to be made, you can do other task, but with synchronous, you have to wait for the pizza to be made before you can do other task.


In my project, instead of using `.then()` with fetches like how the labs have us practiced, I have learned a new way(during project week) to handle promises which is using `async await` for all my GET request. Async await looks more like synchronous JS because with `await`, JS will not run any of the code underneath the await(in it's same scope) until the promise is resolved with a value, and with await, you will have to put async on your function, for example:

```javascript
static async loadAllPets(category) {
  let request = await fetch("http://localhost:3000/pets")
  let allPets = await request.json()
}
```
`async await` is the same as `.then()` because none of the code inside `.then()` will run until the promise is resolved. The difference is instead having to put code inside of `.then()`, you can just put it underneath. So when the execution hits the await it will start the asynchronous code and it will skip all the rest of the code underneath the await inside the async function and continue or finish executing all of the synchronous code left in your application.

## To Conclude
I think this project was hard, due to the fact that Javascript is so powerful, but the syntax are really confusing comparing to other language that we have been using. And because JS was already hard enough that we were using it to make our first js project along with using Rails that is only for backend. It took me a lot of time trying to understand how to get the data from the backend using Javascript. It was really challenging.  
 
