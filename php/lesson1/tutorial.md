---
layout: page
title: Strings, Integers, Floats &amp; Booleans
---

## Prerequisites

Welcome to the PHP tutorial! PHP is an open source language used to generate
web pages and powers hugely popular platforms like Wordpress, Drupal and the
Laravel framework.

In these tutorials we'll work towards putting together a small website so you
need to have an understanding of HTML and CSS. If you're not familiar with these we recommend completing the tutorials on this

If you already have PHP installed just check through the [installation instructions](php/lesson0/tutorial.html) and make sure that you also have **PsySH** installed

## Introduction

In this tutorial, we're going to look at the basic data types in PHP. These basic
types are known as 'scalar' types:

- **Strings** &ndash; used to display text (think of a 'string' of characters)
- **Integers** &ndash; whole number numeric values e.g. 4, 7, 3000000, 42
- **Floats** &ndash; numbers with a 'floating' point. The floating part means there
  isn't a fixed number of places after the point e.g. 1.2, 43.002, 0.01 are all floats
- **Booleans** &ndash; either 'true' or 'false' it's as simple as that 🤓

In this tutorial we'll work in PsySH the REPL we installed in the
[Installing PHP](/php/lesson0/tutorial.html) tutorial. Fire up your Terminal and type in
`psysh` then press return.

_**Tip**: If you need to exit PsySH press `Ctrl + C`_

## Strings

You may have already seen this coding tradition before. We'll start by printing "Hello, World!"
to the console. Type the following after the PsySH prompt (`>>>`) followed by return:

```php
echo 'Hello, World!'
```

You should see the text `Hello, World!` output on the next line. The `echo` part here is a PHP
language construct which expects to be followed by a String to output. The String is the group
of characters surrounded by single quotes. Try typing your own message.

You can also write Strings using double quotes in PHP. This can be useful when you need to
output a string which _contains_ either single or double quotes. First try this:

```php
echo 'It's PHP day'
```

🐞 Erk! You _should_ have seen an error message about an "unexpected T_STRING". This is because the single quote in `It's` is actually terminating the string early then PHP doesn't understand the `s PHP day'` characters after it. Let's try using double quotes to wrap the same string:


```php
echo "It's PHP day"
```

🎉 you should now see the string output correctly in PsySH.

What if we need to use double quotes in our string? We can do something similar the other way around:

```php
echo '"What larks, Pip" said Joe'
```

There are also some other useful differences between Strings using single and double quotes
but we'll get to those in a later tutorial.


If you have two strings and want to join them together in PHP you use a dot `.` 
The programming term for joining strings together is _concatenation_. Type the following in PsySH and press enter:

```php
echo 'one, ' . 'two, ' . 'three!'
```

## Integers &amp; Floats

You can use integers and floats to perform arithmetic in PHP using a handful of operators. In PsySH type the following
and press return to see the result:

```php
6 - 2
```

or

```php
3 + 9.5
```

Multiplication and division use the `*` and `/` operators:

```php
2.25 * 4
```

or

```php
12 / 3 + 1
```

In the last example the result is 5, as PHP carries out the division before adding 1. If you studied Maths, you might remember the [BODMAS (or BIDMAS)](https://en.wikipedia.org/wiki/Order_of_operations#Mnemonics) mnemonic which describes the order in which operations are carried out. If we want PHP to change this order, so that 12 is divided by the result of 3 + 1, we can use brackets to group the addition:

```php
12 / (3 + 1)
```

We can even use brackets to group brackets if we want to get decadent:

```php
(12 / (3 + 1)) * 8
```

There's also an interesting modulo operator `%` which will give the remainder after dividing one number by another.
Try these out in PsySH:

```php
12 % 4
```

and

```php
11 % 4
```

Modulo might seem a bit strange but it can be useful for checking if a number is odd, even or is divisible by another
without a remainder. Try using modulo 2 `% 2` on some numbers in PsySH e.g.
```
7 % 2
128 % 2
```

If the result is zero `0` then we know the number is even and if not we know it is odd.



## Booleans

Named after Lincolnshire mathematician George Boole who worked on algebraic logic. Booleans represent an on or
off or 'true' / 'false' value and are usually used in control structures to change what's happening in a program.
Use PsySH to evaluate `true` and `false`. Spoiler &ndash; don't get toooo excited 😜

Booleans in PHP are case-insensitive which means all the following are valid `true`, `True`, `FALSE`, `falsE`, `fAlSE`

&hellip; but we'll stick to all lowercase as this is the standard form [agreed by the PHP community](https://www.php-fig.org/psr/psr-12/)
and writing it like `fAlSE` looks a bit crackers and is difficult to read.

## Switching between types

Lastly a quick heads-up about how PHP works with types. Like JavaScript, PHP is a _weakly typed_ language
('type' as in 'types of things' not 'she typed on a keyboard').

This means that PHP will try its best to 'do the right thing' if you use a data type in the wrong place.
As we will see 'doing the right thing' is somewhat subjective. Remember how `echo` expects a String in
our "Hello, World!" example above?

Use PsySH to evaluate this code:

```php
echo true
```

What was the result and was it what you expected? You should have seen a `1` output in PsySH. This 1 is actually a string (rather than an integer).

The reason this happens is that PHP _turns the Boolean into a string_ because that's what `echo`
expects to be given. Similar to JavaScript PHP has some predefined steps for converting between types and these aren't always what you might expect. We use the term 'type coercion' to describe this automatic switching.

You can coerce types manually in PHP. This explicit type coercion is known as 'casting'. Use PsySH and precede
a value with the type you want to convert it to in brackets. One of our scalar values:

- **String**: `(string)`
- **Integer**: `(int)`
- **Float**: `(float)`
- **Boolean**: `(bool)`

Let's use this feature to inspect the result of converting a boolean to a string:

```php
(string)true
```

You'll notice that the value which results is the string `"1"`. Let's see what happens
when we echo a boolean `false`:

```php
echo false
```

🤔 nothing happened? Did it? Let's explicitly cast `false` to a string like we did with
`true` in the previous example. Can you see what the result is? `""` is an _empty_ string
and this is what was `echo`ed to our Terminal.

Let's finish up with a couple of exercises. Ask your coach for help if you get stuck.

Addition:
```php
true + true
```

Use your detective skills along with type casting in PsySH to figure out why the result is 2.

Concatenation (gluing two strings together).
```php
true . true
```

Can you figure out why the result was "11"?

Use PsySH to experiment casting values to different types. Have fun with it and don't
worry about memorising exactly how types are coerced by PHP right now.
Just be aware it does this if you see unexpected values when debugging your programs
and that you can use PsySH to help figure out what happened 😊

## Recap

We learned about the basic data types we'll be working with in PHP:

- String
- Integer
- Float
- Boolean

We also learned how to use PsySH (our REPL) to experiment with PHP types and that we can exit PsySH using `Ctrl + C`.

Next we'll learn how to store these values in [variables and arrays](/php/lesson2/tutorial.html)
