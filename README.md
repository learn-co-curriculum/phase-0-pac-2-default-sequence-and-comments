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

Using SELECTION statements we can make JavaScript "skip" over code if some
Boolean _evaluation_ is (or is not) `true`. Using REPETITION statements, we can
make JavaScript "stay put" on one line and do it over and over until some
Boolean _evaluation_ is (or is not) `true`. The only way to make JavaScript "not
see" a line without a Boolean _evaluation_ at play is to "hide" it from
JavaScript using a _comment_. We'll learn how to do this a bit later in the
lesson but first, let's expand our repl.it skills a bit.

## Using the Code Window in repl.it

So far, we've been using the console window in [repl.it][] and ignoring the code
window. Now we're going to learn how we can use the code window to make it
easier to write, test, and experiment with code. Go ahead and open [repl.it][].

When you open it, you'll see a single line of code in the code window on the
left side:

```js
console.log('Hello, world!')
```

If you click the "Run" button, you will see the message "Hello, world!" written
out in the console window on the right. You will learn more about using
`console.log` a bit later in this section. For now, just know that `console.log`
allows us to write code in the code window and print out results of that code to
the console.

When you pressed run, the REPL _evaluated_ the expression inside the
parentheses, and then printed that value out to the console. In this case, there
is a constant expression inside the parentheses, so that value is what is
output. But we can put other types of expressions in the parentheses as well.

For example, try entering the following into the code window, then press "Run".

```js
sum = 1 + 1;

console.log(sum);
```

You should see the value `2` written to the console.

What do you think will happen if you type the following into the code window and
run it?

```js
console.log(5 * 5);
```

As long as whatever is inside the parentheses _evaluates to a value_ — i.e., as
long as it's an expression — that value will be logged in the console.

So now we know two different ways to check the value of an expression in the
REPL: we can either wrap it in a `console.log` in the code window and press
"Run", or we can enter it directly in the console window and hit enter.

Note that we could also combine the two approaches. Go ahead and enter this into
the code window and click Run:

```js
difference = 10 - 5;
```

Although it doesn't appear that anything happens because nothing is printed to
the console, JavaScript has evaluated the arithmetic expression and that value
is now stored in the variable `difference`. Now type `difference;` in the
_console window_ and hit enter.

Often, it's inconvenient to type or copy/paste code into the console — if you're
working with a large block of code, for example, or if you want to be able to
make multiple changes. Putting code in the code window makes it easier to
correct errors and try different things.

As you work through the curriculum, we encourage you to use [repl.it][] to try
out code samples from the lessons and to experiment with your own examples. Now
that you know how to use the code window, you have another tool at your
disposal.

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
```

If you enter the code above into the repl.it code window and click "Run", you'll
see that nothing happens — which is good! JavaScript has recognized the
commented-out lines as comments and ignored them. If you try "un-commenting out"
one of them and rerunning the code, you'll get a `SyntaxError`.

So far, so good, but we still haven't verified that our code is doing what we
want it to do. Go ahead and check the value of `chorus`. Try it using both of
the methods we've learned: adding a `console.log` of the variable in the code
window, and directly checking its value in the console. Remember that, with
either option, you need to _Run_ the code.

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
```

**Default sequence** satisfies our expectations if we check the value of
`chorus`:

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
```

Now, if we run the code and check the value of `chorus`, it returns:

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

lineFour; // => "Joy to you and me"
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
