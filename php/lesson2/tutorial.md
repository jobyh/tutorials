---
layout: page
title: Variables and Arrays
---

In this tutorial we'll look at ways we can store values in our program
and why we might want to do that. We will focus on:

- Variables
- Arrays



We'll use PsySH again to explore these types so once again fire up your
Terminal and launch PsySH.

_**Reminder:** Launch PsySH by typing `psysh` in your Terminal then pressing return. You can exit PsySH with `Ctrl + C`._

## Variables

Variables give us a way to store values so we can use them later in our program
or as a placeholder to work with values we don't yet know.


Let's create a variable. Type the follwing in PsySH:

```php
$luckyNumber = 7;
```

Great! We've created a variable and assigned it with the value 7. In PHP all variables
start with a dollar sign `$` and can contain letters, numbers or underscores.
The only restriction is that they must _not start_ with a number e.g. `$3` would
cause an error.


Little pieces of code like above which tell the PHP interpreter to do something are
called statements. All statements in PHP **must** end with a semicolon `;` like a full-stop
at the end of a sentence. The programming name for the semicolon is a _statement terminator_.

PsySH will forgive you if you forget the semi-colon but be warned you **must**
include them in your actual programs.

If you now type the name of the variable (`$luckyNumber`) into PsySH and press return you should see
the value which we stored in it. Wherever we use our new variable PHP will replace it
behind the scenes with the value 7. Try this in PsySH:

```php
$luckyNumber * 3
```

If we decide we want to store something else in our variable we can update it by
using the _assignment operator_ again:

```php
$luckyNumber = 'seven';
```

Remember the _concatenation_ operator from the previous tutorial which glues strings together?
Try using it with our new variable:

```php
'My lucky number is ' . $luckyNumber
```

Let's try a couple of experiments. Use PsySH to see the result of these:

**Single** quotes:
```php
'My lucky number is $luckyNumber'
```

**Double** quotes ✨:
```php
"My lucky number is $luckyNumber"
```

### A Case of Case
Let's take a moment to talk about case. If we can use letters and underscores why did we choose
to name our variable `$luckyNumber` and not `$lucky_number` or `$LUCKYNUMBER`?

After a programming language has been around for a while developers start doing things in certain ways
so that it's easier to read each other's code and understand what's going on. This is particularly
important if you're working in a team or sharing code with others in the open source community.

The way we separate words in variable names (and other things we'll learn about later) is referred
to as 'case'. Three you may have seen before are camel case, snake case and kebab case:

- `thisIsCamelCase`: The first letter of each word (but not the first letter) is capitalised and it looks like the humps on a camel &ndash; popular in JavaScript
- `this_is_snake_case`: Words are separated by and underscore  which appear to slither along the ground like a snake &ndash; the 'Pythonic' way in Python
- `this-is-kebab-case`: Words are separated by a hyphen which makes them appear to have been skewered like a shish-kebab &ndash; HTML attributes & CSS classes

In PHP the convention most commonly used by the community for variables is `camelCase` so that's what we'll
use in these tutorials.


## Arrays
Arrays in PHP (like in other languages) are a container for storing values.
```php
[2, 'a', true, 7]
```