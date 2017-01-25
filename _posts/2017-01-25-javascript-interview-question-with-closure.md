---
title: "A tricky JavaScript interview using closures"
read_time: true 
categories:  
  - guides
tags:
  - closure
  - function
  - javascript
  - javascript interview
  - interview question

#modified: 2017-01-25T14:12:01-04:00

---
Here is a tricky JavaScript interview question, that involves closures. What is the result of the following code snippet?

```javascript

for (var i = 1; i<=5; i++){
    setTimeout(function(){
        console.log("i: " + i)
        }, i *1000);
}

```

Our intuition would be that this will display the numbers from 1 to 5. But does it? The i at the end of the loop ends up with 6. By the time the functions are running, i is already 6. 

* The result is 6 6 6 6 6

Why don't we have 5 different i? We seem to think that these functions are getting a whole new i for each iterations of the loop.

BUT there are 5 different functions that are closing over the exact same global scope. Like writing setTimeout() one after another. 5 separate anon functions close over one scop - the global scope that has only one i in it.

* How to solve this problem such that numbers from 1 to 5 are printed?

The answer is IIFY. Functions create scope. Put a IIFY inside of the loop so that each loop gets own i.

```javascript

for (var i = 1; i<=5; i++){
    (function(i){setTimeout(function(){
        console.log("i: " + i)
        }, i *1000);
        })(i);
}
```

Result: 1 2 3 4 5

Each function is closing over an iteration scope rather than the global scope.

<h2>What other tricky JavaScript interview questions do you know? Share them here!</h2>

---
