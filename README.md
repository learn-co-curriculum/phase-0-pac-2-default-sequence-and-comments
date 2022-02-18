# Default Sequence and Comments

## Learning Goals

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
JavaScript using a _comment_.

Be sure to "play along" with the examples below in [replit][]. We need to build
comfort with working along with the lessons.

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

If you enter the code above into the REPL's code window and click "Run", you'll
see that nothing happens — which is good! JavaScript has recognized the
commented-out lines as comments and ignored them. If you try "un-commenting out"
one of them and rerunning the code, you'll get a `SyntaxError`.

So far, so good, but we still haven't verified that our code is doing what we
want it to do. Go ahead and check the value of `chorus`. Try it using both of
the methods we've learned: adding a `console.log()` of the variable in the code
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

[replit]: https://replit.com/languages/javascript
