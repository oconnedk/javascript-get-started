# Input Validation

Why validation?

Well, sometimes users will become confused by a question - maybe it wasn't phrased right, or maybe they just weren't thinking straight.

It is pretty vital that we ensure that when we ask for a certain type of input, that type of input has been provided.

If I ask for a number I really should validate that a number has been provided.

### Questions To Ask Yourself

- is empty input allowed?
- is it a number?
  - is it a whole number or decimal?
  - what's are the limits (minimum or maximum value)?
- is it a date?

### User Input

In our examples so far we've been using the `prompt` function to get input from the user. As well as the prompt (the message displayed to the user), there is a box for the user to enter their input as well as **OK** and **Cancel** buttons. What do you think happens if the user just presses the **Enter** button without entering any value or the **Cancel** button?

You can [try it out, here](https://jsfiddle.net/oconnedk/q4n0oyks/). Run it twice: once pressing "Enter", the second time hitting the "Cancel" button.

> **Note:**
> You will need the "inspector" console window open (*F12* in Chrome) to see the output.
> More info [here](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_are_browser_developer_tools)
> Once you have the inspector/ Developer Tools window open, select the "console" tab

So, we can now see that it's possible the user to enter "nothing". And there are two versions of nothing. One where they just press **OK**, which is just passed through as an empty string (""), the other where they press **Cancel** (or press the "escape" button), which results in the special **null** value.

So, back on-topic: just because we ask for input, or ask for a number doesn't mean we'll get a number or even input , which is where *validation* comes in.

So, "number validation" for example, needs to cater for
- null (e.g. where "Cancel" is pressed)
- empty (e.g. where "Enter" is pressed, but no value entered)
- an actual value. Note that prompt [*always* provides a string value](https://developer.mozilla.org/en-US/docs/Web/API/Window/prompt) - even if you enter something which "looks like" a number. E.g. "3.141592"


### To-Do

- Debugging using browser
- Assignments
