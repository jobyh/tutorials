---
layout: page
title: Variables and Arrays
---

In this tutorial we'll look at ways we can store values in our program. We will focus on:

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
include them in your actual programs as we'll see later.

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

_**Tip:** If you want to clear the screen in PsySH press `Ctrl + L`_

### A Case of Camels 🐫

Let's take a moment to talk about case. If we can use letters and underscores why did we choose
to name our variable `$luckyNumber` and not `$lucky_number` or `$LUCKYNUMBER`?

After a programming language has been around for a while developers start doing things in certain ways
so that it's easier to read each other's code and understand what's going on. This is particularly
important if you're working in a team or sharing code with others in the open source community.

The way we separate words in variable names (and other things we'll learn about later) is referred
to as 'case'. Three you may have seen before are camel case, snake case and kebab case:

- `thisIsCamelCase`: The first letter of each word (but not the first letter) is capitalised and it looks like the humps on a camel &ndash; popular in JavaScript
- `this_is_snake_case`: Words are separated by and underscore which appear to slither along the ground like a snake &ndash; the 'Pythonic' way in Python
- `this-is-kebab-case`: Words are separated by a hyphen which makes them appear to have been skewered like a shish-kebab &ndash; HTML attributes & CSS classes

In modern PHP the convention most commonly used by the community for variables is `camelCase` so that's what we'll
use in these tutorials.

## Arrays

### A List of Values

Arrays are another type in PHP. Where strings, integers, floats and booleans
are simple types Arrays are known as _compound types_. This means that they
can be made up of other types.

Arrays are created by wrapping a comma-separated list of values in square
brackets. Let's use PsySH to create an array of strings and assign it to
a variable.

```php
$numbers = ['one', 'two', 'three'];
```

_**Tip:** There is an old way of creating arrays `array('one', 'two', 'three')` but we'll stick to square brackets._

If you check the value of `$numbers` using PsySH you'll see that all our values one to three
have been stored. So how can we access the values one at a time?

Try this:

```php
$numbers[0]
```

We access items in an array using the _index_ of the item we
want. The index is an integer starting from zero for the first item.
Try accessing the other items in the array.

If you tried to access an item at an index lower than 0 or greater than
2 you will have seen an "Undefined offset" error notice. This is PHP's
way of telling you there isn't anything at that index.

What do you think will happen when we use our _assignment operator_ like this in PsySH?

```php
$numbers[1] = 2;
```

Output `$numbers` and see what happened. Let's add a Boolean to the end of our array:

```php
$numbers[] = true;
```

Now output `$numbers` again to see what happened. Try adding some other
values to the array.

Arrays can contain values of any of the types we have learned about already
&ndash; even arrays!

```php
$numbers[3] = [4.1, 4.2];
```

Use PsySH to output `$numbers`. What do you think you will get if you output `$numbers[3][1]`? Give it a go!

### A Map of Values

No coding tutorial would be complete without a pirate themed section, right?
Arrr ☠.

As well as storing a _list_ of values Arrays can be used to store a _map_ of
values:

```php
$anneBonny = ['hat' => 'tricorn', 'weapon' => 'pistol', 'dubloons' = > 107];
```

This form lets us specify custom indexes for our array. If we want to know
how many dubloons our pirate has we can access the value like this:

```php
$anneBonny['dubloons']
```

The term _map_ means a mapping between one value and another. In the example
above the String `'weapon'` was _mapped_ to the Integer `107`. When we use an
Array as a map we use a **fat arrow** `=>` to map a _key_ to a _value_. Notice
that these _key_ `=>` _value_ pairs are comma separated like in our list array.

Adding a new _value_ to the Array is done by also specifying the new _key_.

```php
$anneBonny['captured'] = true;
```

Using an array in this way can be useful for grouping values together to
describe real world things which are represented in your program. Arrays
in this form can also be nested. Let's create an array map of pirates.

Follow along in PsySH &ndash; you can copy and paste the longer lines
if that's easier. Because these array items are quite long at we'll start
by creating an empty array&hellip;

```php
$pirates = [];
```

&hellip;then assigning values one by one:

```php
$pirates['Anne Bonny'] = ['hat' => 'tricorn', 'weapon' => 'pistol', 'dubloons' => 107, 'captured' => true];
$pirates['Mary Read'] = ['hat' => 'tricorn', 'weapon' => 'cutlass', 'dubloons' => 83];
$pirates['John Rackham'] = ['hat' => 'tricorn', 'weapon' => 'dagger', 'dubloons' => 11, 'captured' => true];
```

Now all our pirates are stored in the same place and we can access them by name.
What weapon did John Rackham wield?

```php
$pirates['John Rackham']['weapon']
```

See if you can figure out how to add the `'captured'` property for Mary Read
with a `true` or `false` Boolean value. Assign the item directly &ndash; don't just edit whole array above and paste it in again. Get your coach to help if you get stuck.

## Recap

We learned a lot! First up we learned how to create variables to store
values. Then we saw how Arrays in PHP can be used to store a _list_ of
values which can be accessed by a numeric _index_. Lastly we learned
that Arrays can also be used as a _map_ where custom _keys_ are used
to access _values_.

Next up we'll be looking at using all we've learned so far with
logic and loops to write a simple program.
