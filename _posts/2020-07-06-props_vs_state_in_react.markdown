---
layout: post
title:      "Props vs State in React"
date:       2020-07-06 20:50:41 +0000
permalink:  props_vs_state_in_react
---

Trying to differentiate state and prop would be one of the most conceptually confusing for beginners in React, so I break it down into points.


**Props(properies)** 

*  Components receive data from outside the component with props.

* Are what we use to pass data between our components in React which it only goes from parent to child component. So components receive data from parent component with props.


* Props can be anything. they can be strings, arrays, objects, functions, etc. **Callback function**  can also be passed as prop to initiate it's state changes(updating state) from the child component.


* One limit to props is that it is immutable, meaning you shouldn't ever directly change the value of props.



**State**

* Components can create and manage their own local state

* State is mutatable

* When state changes, it trigger updates in components

* Great thing about state is that it'll only update part of the app component that is influence by the data changes instead of updating the whole app.

* State should not be modified directly, but it can be modified with a special method called `setState` (Class Component) **OR** using React hook (Functional Component)


*NOTE: *

*From our bootcamp curriculum, we were taught that state could only be used in class components, and Functional component is used for stateless component. That's because it was this way in the earlier days.*

*However, after the introduction of React Hooks, state can now be used both in class and functional components.*






