---
layout: post
title:      "React&Redux Project"
date:       2020-06-22 03:27:33 +0000
permalink:  working_for_react_project_will_be_updated
---

The period of this final section in the curriculum was not easy, so in the last three days before the project is due, I decided for last minute topic change for my React & Redux Final Project, and I decided to make a Pet Diary App. It was one of the very overwhelming period in my life. The period of COVID-19, BLM Protest or Riot happens, and a period when one of my lovely pet passed away because I didn't notice he got stuck somewhere when I was working on my project in another room. And that is why I decided to change a topic as Pet Diary two days after he passed. 

This app is very simple, it is a first person app where you don't share your stories with others, but to keep it to yourself when you sometimes just need a moment looking back at memories you shared with them. The main two pages are Pet List and Diaries(or with filter). The purpose of your Pet List page is to keep track of all the pets you had/have. With the data that is store for pet list was only their `name` and `birth_date`, once the user input those two info, the age will be automatically calculated. This list is needed if you want to create a diary for them, and why it's there on it's own page because for me, I don't remember all of the birth date when their birth date were all estimated, and when you have many pets at once, it is hard to keep track of the year that they were born. 

Once you got the pet info down, it'll then can be use in the Diaries page where the form is also in there. You will need to select a pet you made in the list in order to write their diary.

The structure of my frontend is a bit more in detailed...
```
├── public
├── src
│   ├── api(where you fetch)
│   │   ├── (model1)API
│   │   └── (model2)API
│   ├── components
│   │   ├── (model1)
│   │   │   ├── components for model 1
│   │   │   └── components for model 1
│   │   ├── (model2)
│   │   │   ├── components for model 2
│   │   │   └── components for model 2
│   │   ├── layout(folder)
│   │   ├── App.js
│   │   ├── Container Component 1.js
│   │   ├── Container Component 2.js 
│   │   └── etc...
│   ├── redux
│   │   ├── actions(folder)
│   │   ├── reducers(folder)
│   │   └── configStore(where I set up compose enhancer and store)
│   ├── styles (folder)
│   └── index.js
└── README.md
```
I guess you can create as many folders as you want, but just to **NOTE** that the more folder you created, the harder for you to find your file when you want to import them. I sometimes likes it more in detail because then it'll be easier for me to find the folder when I need to modify something, but 1/5 of the project time, I was counting my folders when I want to import a file from certain folder.

 
