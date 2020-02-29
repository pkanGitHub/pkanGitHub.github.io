---
layout: post
title:      "Rails Portfolio Project"
date:       2020-02-24 01:15:04 +0000
permalink:  rails_portfolio_project
---


This Rails project was definitely not easy. If you are going to the last half of Rails section, it can be hard, but you should probably start thinking what you want your models and join table be. I messed up and create a brand new project while I've already spent a week on it because of what I chose to be my join table became really complicated with how it should be structured in the controllers and routes. It can also be very complicated when you have *nested routes* which is also a requirement in the project. Be sure on what you are nesting because the path can be very messy or confusing.For example, in my project, I have song and song_review model, which when I nest it, it became `new song_song_review`, I used to have user as a outer route, so it became `new_user_song_song_review` etc, you get the idea. So for those who are going to be doing the project soon, think as throughly as you can before you start making your models.

For my this new project, I decided to make a music blog where users can review/write blogs for their favorite songs. But what I wasn't thinking is the way I want it doesn't contain *many-to-many* relationship that was also required in the project. So I had to do a lot of thoughts changing while doing this project. AND which I ended up with having 1 song and have many users write something like comments/their reviews below whichever songs they want to comment on. Everything didn't end up with what I've planned mainly because I wasn't able to get through the labs knowing everything I need to know before the project week start. It is a very hard project by far. However, I spent way more time on this project and I get to figures things out along the way. 

## Important Concepts I Wish I Understand Before Starting On Project: 
### 1. These are my simple models association:

```
User
has_many :songs

Song
has_many :users

SongReview
```
#### Many to Many Relationship & Many-Through
With user and song in real life, user could have many songs, as well as songs have many users listening to. So *many-to-many* would make sense, but what if I now have information like reviews I want to store in? Would I store in User or Song? That is where a Join Table(Many-Through) comes in. 
And here is an example that helped me understand [here](https://support.airtable.com/hc/en-us/articles/218734758-A-beginner-s-guide-to-many-to-many-relationships-and-junction-tables#junction).
```
user
has_many :song_reviews
has_many :songs, through: :songs_reviews

song
has_many :song_reviews
has_many :users, through: :songs_reviews


song_review
belongs_to :user
belongs_to :song
```
### 2. Class Level AR Scope Method
Maybe because I didn't get to finish the lab before the start of project, THAT I don't remember anything with scope related other than the Admin Scope Section with routes. Although it is easy to understand, it still took me a while to figure out what exactly I need to do with this scope method. So basically when we need this class scope method is because we can make filter for our app. This is one of the scope method example I use in my Project to show only that certain artist from the list.

```
 def self.filter_for_artist(artist)
     Song.where(artist_name: artist)
 end
```

### 3. Devise and Omniauth
Probably without our cohort lead, Jake's walkthrough video, I wouldn't be able to set up devise and omniauth that easily especially they are the concept you learn 'RIGHT' before Rails project. It took me several days to actually understand how devise already have mostly everything that we need for user set up once you have devise set up. Maybe just because how overwhelming I was when I started the project so that I didn't realized there is some documentation in the Devise github which tells what devise has provided us. Once I understand that everything else just makes more sense.

## To Conclude
I have learned a lot while working on this project along with my awesome cohorts who have helped me by taking their time explaining concepts more in detail so that I can understand it better. I also believe it'll be much more fun if I know how all the Rails Magic works before the project begins because those magic can be confusing since you don't know why it is working behind the scene. Thanks to my cohort, Sara, who cheered me up while I know I don't have much time left for it. We both actually start over on our project on the same day which only left us less than a week to work on before it was due, but I was able to finish it overall, I am really thankful from her encouragement and with her kind words.










