# Programming as Conversation 2: Default Sequence and Comments

## Learning Goals

* Recognize the comment character
* Add a comment to code
* Comment-Out code

## Introduction

As said in our introduction:

> The sequence statement isn't so much a statement, as an assumption. Ruby, by
> default, will read our code according to the rules of a **default sequence**:
> "every line, top to bottom, left to right as ruled by order of operations."

Using SELECTION statements we'll make Ruby "skip" over code if some Boolean
_evaluation_ is (or is not) `true`. Using REPETITION statements, we'll make
Ruby "stay put" on one line and do it over and over until some Boolean
_evaluation_ is (or is not) `true`. The only way to make Ruby "not see" a line
without a Boolean _evaluation_ at play is to "hide" it from Ruby using a
_comment_.

Since this is our first lesson using the Learn In-Browser IDE, we'll step
through the process of getting a code environment together.

1. Create a new file in the Learn In-Browser IDE. We can call this file
   `learning-comments.rb`
2. Type in (better than copy-paste!) the code samples
3. Run the Ruby code with `ruby learning-comments.rb`
4. Edit the file and put in new examples as needed

Be sure to "play along" by keying in this code into your own file and running
it. We need to build comfort with working along with the lessons.

## Recognize the Comment Character

We can exclude a line from the **default sequence** by starting the line with
the comment character: `#`. After Ruby sees a `#`, it will ignore from the `#`
to the next line.

Be careful! A comment placed in the middle of an expression will confuse Ruby.

```ruby
# Don't do this:
puts ( 1 #+ 1)
```

## Add a Comment to Code

Comments are **primarily** used to provide references or explanations about
what's going on in code.

```ruby
# Perform a constant expression evaluation
3
# Assign constant 3 to bare-word variable triangle_sides
`triangle_sides`
```

Comments such as these are not particularly helpful. They're just restating
what the code does. More often we add comments with motivation, or references,
or blog posts, or bug reports. See the first line in this example:

```ruby
# From the Three Dog Night song: "Joy to the World (Jeremiah was a Bullfrog)"
puts "Joy to the world"
puts "All the boys and girls"
puts "Joy to the fishes in the deep blue sea"
puts "Joy to you and me"
```

> **A-HA! Moment**. The "return value" documentation shorthand `#=>` starts
> with a comment character. That means what's after `#` is ignored. That's why
> it's used as an "in-code" documentation convention.

## Comment-Out code

Another way to use comments is to "comment-out" code, to "hide" or "mute" buggy
or unused code from the **default sequence**.

```ruby
puts "Joy to the world"
puts "All the boys and girls"
puts "Joy to the fishes in the deep blue sea"
puts "Joy to you and me"
```

**Default sequence** satisfies our expectations by printing out:

```text
Joy to the world
All the boys and girls
Joy to the fishes in the deep blue sea
Joy to you and me
```

Now let's "comment out" the third line.

```ruby
puts "Joy to the world"
puts "All the boys and girls"
# puts "Joy to the fishes in the deep blue sea"
puts "Joy to you and me"
```

If we run this code, it produces:

```text
Joy to the world
All the boys and girls
Joy to you and me
```

As a rule of thumb, try to comment out from the beginning of the line to the
end. As you get more comfortable with Ruby, you might find clever ways to use
comments, but best keep things simple now.

Here's a more complex example of us commenting out code.

```ruby
# name = "Byron"
name = "Luca"

puts "We're sorry, but per health inspector's rules, #{name} is not allowed in
the store."

#=> We're sorry, but per health inspector's rules, Luca is not allowed in the store.
```

We can swap the comments:

```ruby
name = "Byron"
# name = "Luca"

puts "We're sorry, but per health inspector's rules, #{name} is not allowed in
the store."

#=> We're sorry, but per health inspector's rules, Byron is not allowed in the store.
```

It's common for developers to test two code paths (in effect, doing a selection
statement's work by-hand!) by "commenting-out" and "commenting-back-in" code.

## Conclusion

The **default sequence** is how Ruby reads and executes each of the statements
and commands in a Ruby file. To "hide" a line of code from being seen by Ruby,
start the line with a `#`. We use comments to provide lightweight documentation
or to hide code while we debug or test it.
