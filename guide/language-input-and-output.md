# Input and Output

A program with no input or output would be a pretty limited thing.

We've already seen a basic way of displaying output (`alert`) and requesting input (`prompt`). They are both functions (recap [here](/guide/language-basics.md#functions) if you need).
This is how to use them:

```javascript
alert("This is a message");
var message = "This is a message";
alert(message);
```

The calls to `alert` will result in the same message, "This is a message" being displayed twice. The second assigns the variable `message` with the value.

```javascript
prompt("How are you?");
var name = prompt("Enter your name");
alert(name);
```

Because both `alert` and `prompt` are functions they can return a value. As it happens, `alert` doesn't - it just displays a message to the window, there's no need for it to return a value.

`prompt` on the other hand accepts a parameter (`message`) *and* returns a value - the value entered by the user.

Can you see the problem with line 1: `prompt("How are you?");`?

It asks the user a question ("How are you?"), but doesn't capture the response. It's like asking someone a question but not listening to the answer.

Line 2 assigns the variable `name` with the value which the user has entered for their name.

Now I say they've entered their name, but there is nothing stopping the user from just entering nothing, or even: `3.141592`, if they fancied.

### Validation

[Keep reading](/guide/language-validation.md)
