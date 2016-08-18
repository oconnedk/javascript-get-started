# Operators and Assignment

Operators perform *operations* like addition (```+```), subtraction (```-```), multiplication (```*```) and other mathematical operations. 

    var sum = 5 + 6;

The above declares the variable ```sum```, which is *assigned* the result of the *operation* 5 plus 6.

Like standard maths, you can use brackets to override the default mathematical operation order. Like this:

    var sum = (5 * (7 + 3)) / 10;

Declares the variable ```sum``` which will add 7 to 3, multiply it by 5 and divide that result by 10, giving the result: 5.

Strings can also be added, but onlike numbers this results in the string being *concatenated* (joined), like this:

    var sum = "5" + "6";

In the first example, we added the *numbers* ```5``` and ```6```, now we are adding ("concatenating")  the *strings* ```"5"``` and ```"6"```, which results in ```sum``` having the value: ```"56"```.

Concatenation can be useful. Combining what we've seen with *functions*, *assignment* and *concatenation* we can do this:

    var name = prompt("What is your name?");
    alert("Hello " + name);

Here, we use the in-built function ```prompt``` (on line 1) which causes a box to be displayed, prompting the user for input. The *constant string*, ```"What is your name?"``` appears in the box. Once the user enters a value, the second line *concatenates* the *constant* ```"Hello "``` and the variable ```name``` and uses the in-built function ```alert``` (line 2) which can display a value to the window.
So, if the user enters the value: Dave, the result will be: "Hello Dave". Try it out [here](https://jsfiddle.net/oconnedk/qpfpp7wq/).
