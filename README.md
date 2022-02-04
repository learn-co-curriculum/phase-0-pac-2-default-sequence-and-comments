# Default Sequence and Comments

## Learning Goals

* Use the code window in repl.it to try out code
* Recognize the comment marker
* Add a comment to code
* 'Comment out' code

## Introduction

As said in the introduction to this section:

> JavaScript by default will read our code according to the rules of a **default
> sequence** or **default flow**: "every line, top to bottom, left to right as
> ruled by order of operations."

Using SELECTION statements we can make JavaScript "skip" over code if some Boolean
_evaluation_ is (or is not) `true`. Using REPETITION statements, we can make
JavaScript "stay put" on one line and do it over and over until some Boolean
_evaluation_ is (or is not) `true`. The only way to make JavaScript "not see" a line
without a Boolean _evaluation_ at play is to "hide" it from JavaScript using a
_comment_.

## Using the Code Window in repl.it

In this lesson, we'll learn how to expand our use of [repl.it][] to make use of
the code window in addition to the console window. Go ahead and open [repl.it][]
now.

When you open it, you'll see a single line of code in the window on the left
side:

```js
console.log('Hello, world!')
```

If you click the "Run" button, you will see the message "Hello, world!" written
out in the console window. You will learn more about using `console.log` a bit
later in this section. For our purposes now, just know that `console.log` is how
we can get the repl to print out the results of code that is entered in the code
window.

When you press run, the repl _evaluates_ the expression inside the parentheses,
and then prints that value out to the console. This gives us another option for
checking the value of variables and other expressions, in addition to running
code directly in the console.

For example, try entering the following into the code window, then press "Run".

```js
sum = 1 + 1;

console.log(sum);
```

You should see the value `2` written to the console.

What do you think will happen if you type this into the code window and run it:

```js
console.log(5 * 5);
```

As long as whatever is inside the parentheses _evaluates to a value_ — i.e., as
long as it's an expression — that value will be logged in the console.

Note that we could also combine the two approaches. Go ahead and enter this into
the code window and click Run:

```js
difference = 10 - 5;
```

Although it doesn't appear that anything happens — nothing is printed out in the
console — JavaScript has evaluated the value and it is now stored in the
variable `difference`. Now try typing `difference;` in the _console window_ then
hit enter.

Often, it's inconvenient to type or copy/paste code into the console — if you're
working with a large block of code, for example. In addition, putting code in
the code window makes it easier to correct errors and experiment with the code.

As you work through the curriculum, we encourage you to use [repl.it][] to try out
code samples from the lessons and to experiment with your own examples. Using the
code window will make it easier to do that.

## Recognize the Comment Marker

We can exclude a line from the **default sequence** by starting the line with
the comment marker: `//`. After JavaScript sees a `//`, it will ignore from the
`//` to the next line.

Be careful! A comment placed in the middle of an expression can confuse JavaScript.

```js
// Don't do this:
const sum = ( 1 //+ 1);
```

As a rule of thumb, try to comment out whole lines only (i.e., place the comment
marker at the beginning of the line) to reduce the chances of breaking your code.
While you _can_ place comments within a line of code, it's best to keep things simple
for now.

## Add a Comment to Code

Comments are **primarily** used to provide references or explanations about
what's going on in code.

```js
// Perform a constant expression evaluation
3;
// Assign constant 3 to variable triangleSides
const triangleSides = 3;
```

Comments such as these are not particularly helpful. They're just restating
what the code does. More often we add comments with motivation, or references,
or blog posts, or bug reports:

```js
// From the Three Dog Night song: "Joy to the World (Jeremiah was a Bullfrog)"
const lineOne = "Joy to the world";
const lineTwo = "All the boys and girls";
const lineThree = "Joy to the fishes in the deep blue sea";
const lineFour = "Joy to you and me";

// The '\n' inserts a new line into the string
const chorus = `${lineOne}\n${lineTwo}\n${lineThree}\n${lineFour}`;

chorus;
```

> **A-HA! Moment**. Recall that the "return value" documentation shorthand
> `//=>` starts with a comment marker. This indicates that what's after `//` is
> not part of the code itself. That's why it's used as an "in-code"
> documentation convention.

## Comment Out code

Another way to use comments is to "comment out" code, to "hide" or "mute" buggy
or unused code from the **default sequence**.

With our current code:

```js
const lineOne = "Joy to the world";
const lineTwo = "All the boys and girls";
const lineThree = "Joy to the fishes in the deep blue sea";
const lineFour = "Joy to you and me";

const chorus = `${lineOne}\n${lineTwo}\n${lineThree}\n${lineFour}`;

chorus;
```

**Default sequence** satisfies our expectations by returning:

```text
Joy to the world
All the boys and girls
Joy to the fishes in the deep blue sea
Joy to you and me
```

Now let's "comment out" `lineThree`. We'll also need to modify `chorus`
accordingly. (If you aren't sure why, try **just** commenting out `lineThree` in
your REPL and see what happens when you run the code.) We'll comment out the
current version of `chorus` to save it and modify a copy:

```js
const lineOne = "Joy to the world";
const lineTwo = "All the boys and girls";
//const lineThree = "Joy to the fishes in the deep blue sea";
const lineFour = "Joy to you and me";

// const chorus = `${lineOne}\n${lineTwo}\n${lineThree}\n${lineFour}`;
const chorus = `${lineOne}\n${lineTwo}\n${lineFour}`;

chorus;

```

If we run this code, it returns:

```text
Joy to the world
All the boys and girls
Joy to you and me
```

If we want to go back to the original version, we simply "comment back in"
`lineThree` and the original `chorus` variable, and comment out or delete the
modified version of `chorus`.

If we want to comment out _multiple_ lines, we can either place the comment
marker at the beginning of each line, _or_ we can wrap the lines with `/*` and
`*/`:

```js
/*
const lineOne = "Joy to the world";
const lineTwo = "All the boys and girls";
const lineThree = "Joy to the fishes in the deep blue sea"; 
*/
const lineFour = "Joy to you and me";

lineFour;
```

It's common for developers to test two code paths (in effect, doing a selection
statement's work by hand!) by "commenting out" and "commenting back in" code.

## Conclusion

The **default sequence** is how JavaScript reads and executes each of the
statements and commands in JavaScript code. To "hide" a line of code from being
seen by the JavaScript engine, start the line with the comment marker `//`. We
use comments to provide lightweight documentation or to hide code while we debug
or test it.

[repl.it]: https://repl.it/languages/javascript