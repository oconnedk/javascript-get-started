# The Language

Keeping things simple, JavaScript consists of:

- constants
- variables
- operators
- assignments
- conditions
- blocks
- functions
- statements
- loops
 
|What|JavaScript Example|
|---|---|
|constant|```12``` or ```"some words"```. They are both constants. 12 will always be 12.|
|variable|```var count = 1;``` *count* is a variable. It's value may change.|
|operator|```5 + 5``` or ```20 / 3``` or ```3 * 6``` or ```++``` (add one) or ```--``` (subtract one) and more. ```=``` is an **assignment** operator (see below)|
|assignment|```count = 2``` Assigns the variable *count* with the value 2. **Note:** single =|
|assignment|```count += 2``` Adds 2 to the variable *count*. ```count -= 2``` Takes 2 away from the variable *count*|
|condition|```count == 2``` Checks whether the variable *count* is equal to 2. **Note:** double =|
|block|```{ var count = 1; var x = 2; }```. *count* and *x* are only available between the *{* and *}*|
|function|```function celsiusToFahrenheit(celsius)```. Defines the function *celsiusToFahrenheit* which takes one parameter, *celsius*|
|statement|```if (count == 2) { alert("it's two!"); }```. Checks the variable count and if it's equal to 2 displays a message|
|loop|```for (var count = 1; count < 10; ++count) { alert(i); }```. Will display the messsage 1, then 2, then 3, until 9|
|loop|```while (count < 10) { alert(count); ++count;  }```. Will display the messsage 1, then 2, then 3, until 9|

## Execution Order

JavaScript is processed top-down, looping where necessary. When the code gets to the last line, it has typically finished.

    /*
     * This is a simple piece of JavaScript code
     */
    "use strict";                   // force Strict Mode
    var max = 10;					// variable declaration
    var sum = 0;
    for (var i = 1; i < max; ++i)	// loop
    {
        sum += i;                   // Add the value of i to sum
    }
    alert("The sum is: " + sum);    // Tell the user the sum value

Don't worry too much if you don't understand what's going on above, we'll cover it later.

The piece of code (which you can see in action [here](https://jsfiddle.net/oconnedk/x6d79hbv/2/) is a simple *script* (which is what one page JavaScript programs are typically called) which does this - by line:

1. ```/*``` opens a comment block and ```*/``` closes it. A comment does nothing other than tell the reader what's going on
2. This line is within the comment block, so does nothing
3. The end of the comment block. Also does nothing.
4. ```"use strict";``` tells the JavaScript *interpreter* (more on that, later) to interpret the following script in *strict mode*. Long story short: this is good practice and you should do it.
5. Declares a variable ```max```, initialising with the number ```10```
6. Declares a variable ```sum```, initialising with the number ```0```
7. A ```for``` **loop**. This tells the interpreter to execute the following block (lines 8 - 10) while ```i``` is less than (```<```) 10. 
8. Marks the start of a *block*, which ends at line 10
9. Add the value of ```i``` to ```sum```
10. Ends the block (and hence ends the loop)
11. Displays the sum of 1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 9

The script above runs over lines 8 to 10 nine times, while the value of i is less than 10.
The very last line of the script calls a *function* which displays a box on the screen showing the total.
 

### Loops

Loops cause part of a script to repeat. For example, line 7 in the script above tells the interpreter to run the lines in the block while i is less than ten, incrementing the value of i each time.

#### For Loops

A ```for``` loop is an example of a *definite* loop as we know beforehand how many times the loop will repeat. This is roughly true and is OK for now, but as you will later discover, you can exit a ```for``` loop early.

    for (var i = 1; i < 10; ++i)
    {
        ...
    }

In the above loop, ```i``` would have the value 1 first time around the loop, then 2, then 3 up until 9. It doesn't get to 10 as we have the *condition* ```i < 10``` and 10 is not less than 10.
If we wanted it to go to 10, we could modify it like this:

    for (var i = 1; i <= 10; ++i)
    {
        ...
    }

The ```<=``` in the condition is the key thing that changed. And 10 is <= 10 as it's equal to 10.

A **real-world example of a for loop** could be when a teacher is taking a register: they start from the top of the list until they reach the bottom, marking students present or not.

#### While Loops


A ```while``` loop is an example of an *indefinite* loop as we do not know beforehand how many times the loop will repeat - or if it will even repeat at all. 

You *can* use a while loop like a ```for``` loop, but you should only do so if you have a specific reason.

Here is a simple example of a ```while``` loop:

    var number = 128;
    while (number > 1)
    {
        number = number / 2;
    }

The above will take the variable ```number``` and divide it by 2, repeating until the number is no longer greater than one (e.g. 64, 32, 16, 8, 4 and 2).

This is an example of a loop that will not run at all:
    
    var loopAgain = false;
    while (loopAgain)
    {
        ...
    }

It won't run because the condition it is checking (```loopAgain``` has the value ```false```).

A **real-world example of a while loop** could be a guessing game. I say: "think of a number between 1 and 10" and keep asking you to guess again until you get the number right. Or I may not need to ask you to guess again if you et it right first time.

### Types
|Type|Description|
|---|---|
|String|e.g. ```"hello"```, ```'hello'```, ```"3.1415972"```, ```"172.217.23.14"``` etc|
|Number|e.g. ```1```, ```3.1415972```|
|Boolean|e.g. ```true``` or ```false```|
|Undefined|A special value when a value is not specified. More on this later.|
|Null|A value representing "no value". E.g. a value of ```NULL``` has actually specified, typically to initialise a variable. *Not the same as undefined*.|
|Object|An instance of an object which may be your own object (when using Object-Oriented techniques) or one of the in-built classes (e.g. RegExp).|
|Array|A collection of values - which may be of any type (string, number, boolean, array even), but will typically be of the same type. E.g. a list of names ```["Dave", "Pete", "John"];```|

### Reserved Words

There is a lengthy list of [reserved words](http://www.w3schools.com/js/js_reserved.asp) which you may not use for variable names - mainly because they would cause ambiguity. Many words on that list will not yet be familiar to you, but as you progress you will understand why you are not allowed to use them for anything other than their defined purpose.

Consider this for example:

    var true = false;
    if (true == true)
    {
        console.log("It's true");
    }
    
We are trying to find out whether a variable named *true* is "true". It makes the code ambiguous and is not allowed.    

### Functions

Functions can be in-built to the language (e.g. ```length("ABC")``` - ```length``` will return the length of a string) or user-defined.

Where they are user-defined, it will be either *you* that created the function or someone else (which is the case if you use a *library* - more on that later).

Functions often receive one or more *parameters* and typically *return* a value, so in the example of the ```length``` function, the number 3 would be returned for ```length("ABC")```. We can capture the result in a *variable*:
 
    var nameLength = length("Peter Piper");

So, putting some of what we've learnt so far, that line of code declares a *variable* called ```nameLength``` which is *assigned* with the value of ```length("Peter Piper")```. ```length``` is a function, which in this case is passed a parameter with the *constant string* "Peter Piper".

#### User-defined Functions

Sometimes the functions provided by JavaScript are not quite enough and you want to do something different. That is where you will write you own function. Like this:

    function addValues(lhs, rhs)
    {
        return lhs + rhs;
    }

In case you haven't already figured it out, that function returns the sum of the two variables, ```lhs``` and ```rhs```. And this is how you might call it:

    var sum = addValues(5, 6);

Now, we have a newly-declared *variable*, ```sum``` which has the result of ```5``` + ```6```, so ```11```. ```5``` and ```6``` are *constants* which are passed as *parameters* to the function.

### Operators and Assignments

[Keep reading](/guide/language-operators-assign.md)
