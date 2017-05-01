# JavaScript Variables

## Overview

In this lesson, we'll introduce variables and how to declare them in Javascript. 

## Objectives

1. Explain how to declare a variable in JavaScript
2. Explain what variables are good for
3. Declare a variable without assigning a value
4. Declare and define a variable
5. Explain multi-line variable assignment

## What are Variables?

Sometimes, we need to store a piece of information so that we can refer to it — often multiple times — later on. In real life, we would probably jot down a note in a notebook or on a post-it.

![note](https://i.chzbgr.com/full/4950590208/h52A02E59/)

In programming, we use _variables_. Variables in JavaScript are used to store data that will be used in our program. A variable can point to almost any type of value including numbers, strings, arrays, objects, and functions.

Variables are assigned values using the = operator. Variable names are typically all lower case; in the case of multiple words, the words are joined together using lowerCamelCase.


## Declaring Variables

Lets say I have the variable `word`. We could, if we wanted to, write

``` javascript
word = 'bird'
```

in order to create our variable and assign it the value of the string `'bird'`. Thing is, now we've declared a _global variable_. Global variables can be accessed anywhere in an application, which can lead to strange behavior.

Using a global variable is like passing someone a note on a billboard. Sure, it gets the message across, but way more people than necessary now have the message.

What if, for example, we wanted `word`'s value to be something other than `'bird'` at some point in the application? Or what if we needed to make use of a variable called `word` but not _this particular `word`_?

In the browser, global variables are all properties of `window`. What is `window`? Well, it's the — erm — window in which the browser displays the current page. It holds a whole bunch of things (which is probably obvious), global variables among them.

Accidentally setting variables to "global" is a dangerous, imprecise coding mistake.

### `var`

In the olden days (1995), JavaScript had one way to declare a non-global variable, `var`. Using the keyword `var` creates _local variable_, meaning that it is only accessible inside the current function in which it is declared. (However, this is a bit tricky - If 'var' is not declared *inside* a function, it's actually still global!)

**Flat fact**: What's a function? Well, functions are ways of organizing our code so that we can run it repeatedly. We'll talk more about functions in a bit, but we need to mention them here because they're _vital_ to understanding variable scope in JavaScript (which we will tackle in greater depth when we cover functions). Don't worry too much right now about what exactly a function is; we just want to get used to seeing the word.

Here's how this works — follow along in your console!

``` javascript
// declare the variable
var word

// assign a value to the variable
word = 'bird'

console.log(word) // 'bird'

// assign another value to the variable
word = 'dog'

console.log(word) // 'dog'
```

Now we have declared a local variable `word`, and we can assign and reassign its value as we please.

We can perform variable declaration and assignment on the same line to save space:

``` javascript
var word = 'bird'
```

What does it mean that `word` is a local variable? Well, if we're just entering it in the console, not much — the variable still becomes a property of `window`, meaning... in this case, 'word" is a global variable (as mentioned above). (Go ahead, try typing `window.word` in the console — prepare to be amazed!)

We'll learn more about local and global variables in a later lesson. For now, know that **you should always declare a variable with `var`**.

## Multi-line Variable Assignment

Let's say I needed to declare and define multiple variables. It feels like a lot to have to repeat `var` over and over again. JavaScript allows us to do multi-line variable assignment to alleviate this pain. Every variable must be separated with a comma, and the entire line must end with a semicolon.

Let's condense the below code into one line:

```javascript
var a = 5
var b = 2
var c = 3
var d = 'hello'
var e = 'goodbye'
```

The above is equivalent to:

```javascript
var a = 5,
    b = 2,
    c = 3,
    d = 'hello',
    e = 'goodbye';
```

which can be converted to:

```javascript
var a = 5, b = 2, c = 3, d = 'hello', e = 'goodbye'
```

Try typing each variable in the console. You should see the appropriate values returned for each one.

Personally, we're of the opinion that it's best to declare each variable with its own `var` keyword. The comma fanciness saves a little bit of typing, but at the expense of nonstandard indentation (you're using two spaces, right?) and can introduce a bit of weirdness if we're doing anything other than simple assignment.

## Changing values

Sometimes, information changes — we have to scratch out old notes and scribble in revisions.

In JavaScript, we can simply reassign the new value to the variable.

``` javascript
var myNote = "Get milk"

// later on

myNote = "Get cookies"
```

When we change the value of a variable, _we do not use `var` again_. We simply use the `=` to give the variable a new value.

<p class='util--hide'>View <a href='https://learn.co/lessons/javascript-intro-to-variable-assignment-and-declaration'>JavaScript Variable Assignment and Declaration</a> on Learn.co and start learning to code for free.</p>
