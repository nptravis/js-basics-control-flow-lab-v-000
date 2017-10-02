# Control Flow Lab

## Overview
In this code-along, we will practice working with control flow in JavaScript.

## Objectives
1. Practice writing `if...else if...else` statements.
2. Practice working with the ternary operator.
3. Practice writing `switch` statements.

## Introduction
You have been hired as a contractor for Scuber, a burgeoning startup that helps busy parents transport their children to and from all of their activities on scooters.

Scuber's drivers charge their passengers a variable amount based on how far they need to travel. Modify the `index.js` file to ensure that Scuber's drivers are properly telling their passengers how much the ride will cost.

## Read the Tests
We know that you do not have much experience with testing, so that is why it is very important for you to read the instructions in this and every lab. That being said, reading the tests can often provide supplemental guidance on how to complete a lab. Let's take a look at the first test for this lab together:
```js
var feet;
var city;
var tip;

describe('index.js', function () {
  describe('scuberGreetingForFeet()', function () {
    it('gives customers a free sample if the ride is less than or equal to 400 feet', function () {
      feet = 199
      expect(scuberGreetingForFeet()).to.equal('This one is on me!');
    });

    // tests continue...
  });
});
```

Ok so all of the fancy `describe` words are just there to organize the requirements, and provide a mechanism for what each function should do. By reading the text inside of the `describe` words, we can see that there is some function that should give customers a free sample, where the first 400 feet are free. Then in the next line we see a function called `scuberGreetingForFeet` being executed. Executing the `scuberGreetingForFeet` function should return `"This one is on me!"`.

If we run the tests with the `learn` command, we see that `scuberGreetingForFeet` currently returns `fix scuberGreetingForFeet!`. We can fix this by changing our function `scuberGreetingForFeet` in the `index.js` file. The big insight is that the tests in the `indexTest.js` file are calling the functions that we write the `index.js` file.  Now inside of this test, we see that it sets a variable of `feet` equal to 199.  

When the variable `feet` equals `199`, the `scuberGreetingForFeet` function should return `"This one is on me!"`. That makes sense, considering the text in the `describe` and `it` functions say that the first 400 feet should be free. So the `199` must be indicating the distance in feet of the requested ride.  The line `return taxiResponse` currently returns the variable with `taxiResponse` set to `"fix scuberGreetingForFeet!"`.  Change the code so that it assigns the variable `taxiResponse` to equal `This one is on me!` and the first test will pass.  Now if you look to the next test, you can see that it changes the variable `taxiResponse` to 2001.  When `feet` equals 2001, the function should return `"I will gladly take your thirty bucks."`.  You should make use of an if else statement to `taxiResponse` set equal to different values.  This will have your function return different values.

> Our Changing Variables
How does the code inside of the function have access to the `feet` variable.  Well at the top of the `indexTest.js` file, we declare that variable (along with `tip` and `city`).  Because these variables are not enclosed in a function, they are global meaning that they are accessible throughout our codebase.  So our test first changes the variable of `feet` and then executes our function with the line `scuberGreetingForFeet()`.  This runs the code inside of the `scuberGreetingForFeet()` and returns a different value depending on our value.

So reading tests are essentially like reading the instructions. It's something, we may have avoided for much of our lives, but when it comes to programming, tests fill in the picture of the goal we are trying to accomplish. They run mini-experiments on our code and help us better understand our code and the problem we are solving.

## Instructions
There are three functions you need to fill in:
* `scuberGreetingForFeet()` — Use `if` and `else if` statements to return the correct greeting based on the distance the passenger desires to travel.
* `ternaryCheckCity()` — Use a ternary operator to return the correct response based on the desired destination of the passenger.
* `switchOnCharmFromTip()` — Use a `switch` statement to return a different response based on the generosity of the passenger's tip.

***NOTE***: Remember, each time you save the `index.js` file the test suite in your browser will automatically re-run itself and push the results to Learn. When all of the tests are passing at the end of the lab, the `Run Local Tests` light on the Learn.co lesson page will turn green.

***NOTE***: Beware a gotcha! In JavaScript, you cannot express the concept of 'between' in the following way:
```js
2 < 5 < 4
// => true
```

It seems like that expression should evaluate to `false` because `5` is not less than `4`. However, we're forgetting about the order of operations — let's think about how the JavaScript engine evaluates that expression. First, the engine compares `2 < 5`, which evaluates to `true`. At that point, it's as though the value `true` has replaced `2 < 5` in the expression, resulting in `true < 4`. The engine sees that we're trying to compare a non-number (`true`) against a number (`4`), and under the hood it converts `true` into a number:
```js
Number(true);
// => 1
```

That leaves us with `1 < 4`, which the JavaScript engine correctly evaluates to `true`. Can you figure out how to properly evaluate whether `5` is greater than `2` **AND** `5` is less than `4`? Ponder that as you work through the assignment below.

Good luck!

<p class='util--hide'>View <a href='https://learn.co/lessons/js-basics-flow-control'>Control Flow Lab</a> on Learn.co and start learning to code for free.</p>
