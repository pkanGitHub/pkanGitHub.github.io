---
layout: post
title:      "Redux: Understanding Redux Flow "
date:       2020-07-01 03:08:20 +0000
permalink:  redux_understanding_redux_flow
---


Before I started on my final project, I still find myself confused with the subject React and Redux. However, as I work on them with more familiar topic, it is easier to understand React, but for Redux, lets talk about it... 

I've heard many of my cohorts and friends saying Redux is an overkill for our project, since we only touch on this topic for a short period of time that the project we decided to make isn't going to be big enough to need Redux. So...

## WHY DO WE NEED Redux?

*This may not be the best example, but lets use bank as an example to describe each flow.*

**Redux Cycle =  Action Creator -> Actions -> Dispatch -> Reducers -> Store/State**

**Action Creator** is a function that is going to create or return plain javascript object(Action)  
*Ex. A client in the bank*

**Action** is a "message" to the reducer describing the change wanted inside of our app.  
*Ex. A slip for withdraw or deposit (noun)*

**Dispatch** function is going to take in an action and going to make a copy of that object and passed it off to different places inside of our application.(verb)  
*Ex. Speaking to the teller of what is needed to be done*

**Reducer** is a function that is responsible to taking in an action and some existing amount of data and it's going to process that action and then make some change of the data and then return it, so it can then be use in other location with store.
*Ex. The teller takes the slip and go take the money out of the vault for withdraw, or put the money in for deposit.*


### ---------------------------------------------------------------------
**Middleware(thunk)** is needed when you are working with async code, thunk is the middleware we were taught to use that when the need of middleware comes(for promises), your action creator and action will become async action creator and async action. It is part of your app as it is like a bridge for your API call to your action dispatch. They don't deal with the store directly, but you can't have them to be left out if you want specific job done.  
*Ex. Bank manager. When a client request a large withdraw, tellers needs to get permission from the bank manager before they can continue do what is asked.*


REDUX STORE(Ex. vault): 

This is more of visual look of why the Redux Store is needed in big appliacations.

``` 0*--0--0--0--O--0--0--0--0* ```

Note: The middle `O` is the `App.js` component

lets say the first `0*` is a nested component which is inside of the component on the right and so on. All the way into `App.js` component. Meanwhile, the same for the right end side `0*` sending toward the center.

So `App.js` has 2 component inside of them.  

And lets say the `0*` on the right-end has a thing that changes the state, like for example if you press a button, it'll add 1 to your score. 

But what if your left-end`0*` component also need the access to the score, then all you'll have to do is string all the right `0` together so when you press the button, it'll initiated to right `0*`component and to send it up one by one to the left all the way to the `App.js` just so you can change the state, and also one by one update it all the way to the left-end `0*` so it have access to it. You probably can already tell, if this is a large application, then it gets very tedious.


**SO WHAT REDUX DOES** is to creates a single immutable store and Redux allows components to have access to that store no matter where they're at, which means if you got redux loaded in your app, you can just `connect` the components to Redux and when that component changes the score, it's equally accessible to all your connected components.

So it will automatically update on the left end `0*` without passing all the way from right end `0*` one by one.

## Conclusion
I hope this may help some of you understand Redux better, as it is really complicated as you first encounter them. And it is normal to felt this way. A friend of mine who is working in this field also said, "Developers spend 2-6 months working with redux before they finally understand it", so don't feel like you are not smart enough(like I did, but afterwards I heard the same for most of my cohorts). However, note that Redux can be very useful when we started to work on bigger projects.
