---
title: "Closure for dummies - a complete guide to understanding closures in Javascript"
read_time: true 
categories:  
  - guides
tags:
  - closure
  - function
  - javascript
  - object
  - demo

#modified: 2017-01-25T14:12:01-04:00

---
The concept of closures in Javascript can be hard to grasp at first. However, once you will have that <b>a-ha</b> moment, a new powerful capability of Javascript will have been revealed to you. That's ok, because closures are considered an advanced concept of Javascript.

According to <b>Javascript - the definitive guide, 6th edition</b> a function is a block of JavaScript code that is defined once but may be executed, or invoked, any number of times.

In JavaScript, functions are objects and can be assigned to variables. JavaScript function definitions can be nested within other function, <b>and they have access to any variables that are in the scope where they are defined</b>. 



* Learn closures with  Bob Tabor and cats

<iframe src="https://channel9.msdn.com/Series/Javascript-Fundamentals-Development-for-Absolute-Beginners/Fundamentals-of-JavaScript-Closures-20/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>

Bob defines a closure as <i>a special type of object, that combines a function and the environment in which that function was created.</i> The environment consists of the local variables that were in scope at the time the closure was created , as well as any input parameters that were passed in. We get both the function implementation, as well as its environment.

You are binding some data to a function, storing it as a variable for later usage in the program. 

*Learn closures with a definitive example

Javascript uses <i>lexical scoping</i> - functions are executed using the variable scope that was in effect when they were <b>defined</b> not the variable scope that is in effect when they are invoked. 

<b>Definition 1: Closure</b>  The combination of a function object and a scope (a set of variable bindings) in which the function's variables are resolved, is called a <b>closure</b> in computer science literature.

Every Javascript function is a closure: they are objects and they have a scope chain associated with them. Let us look at an example

```javascript
function counter() {
var n = 0;
    return {
        count: function() { return n++; },
        reset: function() { n = 0; }
    };
}

var c = counter(), d = counter(); // Create two counters
c.count() // => 0
d.count() // => 0: they count independently
c.reset() // reset() and count() methods share state
c.count() // => 0: because we reset c
d.count() // => 1: d was not reset
```

The counter() function returns a "counter" object. The object has two methods:  
    *    count() - returns the next integer
    *    reset() - resets the internal state

The two methods share the acces to the private variable b.
Each invocation of counter() creates a new scope chain and a new private variable

So if you call counter() twice, two counter objects with different private variables will result.

* Master the JavaScript interview : What is a closure?

This article from  <a href="https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-closure-b2f0d2152b36#.s8tp5gf5h" target="_blank">Medium</a>.

<b>Definition 2: (Closures)</b>A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer function’s scope from an inner function. In JavaScript, closures are created every time a function is created, at function creation time.

You see, the definition is simply another flavor of what we know so far.

In a next example, the `.get()` method is defined inside the scope of `getSecret()`, which gives it access to any variables from `getSecret()`, and makes it a privileged method. In this case, the parameter, `secret`. Have a play with closure on JSBin:

<a class="jsbin-embed" href="https://jsbin.com/gareno/4/embed?html,js,output">JS Bin on jsbin.com</a><script src="https://static.jsbin.com/js/embed.min.js?3.40.3"></script>

* Learn closures with Joe

Your skill as a JavaScript developer can be measured by how well you understand closures. <a href="https://code.tutsplus.com/tutorials/closures-in-javascript--cms-24009" target="_blank">Joe says so</a>

<b>Definition 3: (Closures)</b> The idea of closures is accessing variables from outside of the current local scope. From any function you can access the variable that are above the function in the scope hierarchy. 

The idea becomes more useful when we have a function inside another function. Let us see an example below. From the inside() function we can access the firstScope variable from the outside function (because they are functions inside a function).

```javascript

function outside(){
    var firstScope = "one";

    function inside(){
        var secondScope = "two";
        return firstScope + secondScope;
    }

    console.log(inside);
}
```

The result will be: onetwo.

The real benefit comes into play when we actually return the function:

```javascript

function outside(){
    var firstScope = "one";

    return function inside(){
        var secondScope = "two";
        return firstScope + secondScope;
    };
}

var inner = outside();

console.log(inner());
```

The result will  be the same: onetwo. The function returned a value that referenced something from outside the scope. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/1lczrpwwZIE" frameborder="0" allowfullscreen></iframe>

* Scope and closure with Udacity

I like Udacity's take on closures. <a href="https://classroom.udacity.com/courses/ud015/lessons/2593668697/concepts/25411890500923" target="_blank">https://classroom.udacity.com/courses/ud015/lessons/2593668697/concepts/25411890500923</a> No comments needed, just watch for yourself.

* Pluralsight take on closures

The top of the cake is maybe this take of Pluralsight <a href="https://app.pluralsight.com/player?course=advanced-javascript&author=kyle-simpson&name=advanced-javascript-m3&clip=0" target="_blank">https://app.pluralsight.com/player?course=advanced-javascript&author=kyle-simpson&name=advanced-javascript-m3&clip=0</a>

<h2>What practical example have you used to understand closures? Share it here!</h2>

---
