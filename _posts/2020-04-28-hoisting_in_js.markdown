---
layout: post
title:      "Hoisting in JS"
date:       2020-04-28 23:53:15 +0000
permalink:  hoisting_in_js
---


## What is Hoisting? 

When we look up what is hoisting in JS, we will be most likely to get this explaination:
*behavior of moving declarations of variable and function to the top of their current scope. *

what does that mean? 


In JS, there is two phases of hoisting:

1. It is going to scan for all of the declared variable and function when the program runs from top all the way through the end and put them into the memory of Lexical Scope.
2. It is going to start implement the these variable and function from the top, execute them line by line,   since these functions and variable have already been created in the memory.


### Difference Between `let` and `var` in Hoisting

So  lets see how hoisting work in `let` and `var` :

For `var` variable:

```javascript
console.log(num); //output 'undefined'
var num = 10
```

why is it undefined when we are expecting the number 10? 

It is because JS hoist only hoist the declariation, not their assignment which is the value.
So when `num` is called in the console.log, the lexical scope will only initialize it with undefined. And when the execution reached where the assignment is done, it'll then update the value to 10.

Where for `let` variable: 

```javascript
console.log(num); // ReferenceError: num is not defined
let num = 10;
```

why the num is 'not' defined instead of undefined like `var`?

All declarations with function, var, let, ...etc are hoisted in JS, but only `var` is initialized with undefined in lexical scope, while `let` remains uninitialized and it will only to be initialized when their lexical assignment is evaluated during the runtime by the JavaScript engine. Which means it cannot access the variable before it is assigned to a value at where it was declared in the code. 

If after it runs through the code and still can't find the value of `let`,  it will THEN assign the value to undefined.







