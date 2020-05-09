---
layout: page
title: Generating a Web Page
---

Welcome back me hearties! Ahem. In this tutorial we'll see how we can use PHP
to generate some output we can access from our web browser 🙌 . We're going to:

- Set up a project directory like a _hacker_\* 😎 &ndash; our 'Workspace'
- Create a PHP script
- Run a PHP development web server
- View the output of our PHP program in a web browser

You may have heard the term _hacker_ to refer to computer programmers
who use their skills for evil. This is an unfortunate case of news media
co-opting a term and using it only with a negative bias. _Hacker_
in coding culture is generally used to refer to a knowledgeable programmer
and is more like a badge of honour than a mark of shame 😊

## Code Editor

We're going to write a script in PHP in this tutorial so you'll need a code
editor. If your not sure which editor to use I would recommend [Visual Studio Code](https://code.visualstudio.com/)
it's a great editor with PHP support and free to use.

## Workspace

Let's get started by creating a directory (folder) for our project.
Open the Terminal, type

```
cd
```

&hellip;and press return. This command lets us _change directory_ allowing
us to navigate around our computer's filesystem inside the Terminal.
From now on instead of saying _type X and press return_ we'll say _run X_

When we call `cd` on its own we are taken to our _home directory_. If your
username is `Jody` then on MacOS this is located at `/Users/Jody`. On Linux
it is located at `/home/Jody`. Run `pwd` &ndash; what did you see?

`pwd` stands for _**p**rint **w**orking **d**irectory_. The _working directory_
is just Terminal speak for where you currently are in the computer's filesystem.
The output of `pwd` is a _path_ &ndash; a list of directory names separated by
a forward-slash describing a location on the filesystem.

Our home directory is where things like our user settings are stored as well
as personal files like images and text files in the directories `Pictures`
or `Documents`. This is a good place to store our code.

If you're running Ubuntu in Windows using the Windows Subsystem
for Linux (WSL) then your _Windows_ home directory is somewhere different
so we'll need to change to it first:

Windows (WSL) only:
You'll need your username for this. Check what it is by running:

```
whoami
```

Then use it to change to your Windows home directory. If the output
of `whoami` was `jody` then you'd use:

```
cd /mnt/c/Users/jody
```

MacOS, Linux & Windows (WSL):

```
mkdir codebar
```

This command _makes a directory_ with the name we provide &ndash; in this instance `codebar`. Let's navigate the Terminal into our new directory using `cd codebar`.
Run `pwd` again and see that the _working directory_ has changed.

Let's make a directory for this tutorial. Go ahead and use the `mkdir` command
to create one called `php` then use `cd` to navigate inside it.

Lastly we'll create a PHP script and fire up our local webserver. Run the following
command to create a file called `index.php`

```
touch index.php
```

We can check that it was created by listing the files in the _working directory_
using the `ls` command. Go ahead and run it.

PHP provides a handy command to run a built in webserver for _local_ development. Local development means on a developer's computer. The built in
PHP webserver should **never** be used to serve a live site on the web.

Let's fire up a webserver in the current _working directory_ so it has access to
our `index.php` script. Run the following by pasting it into the Terminal:

```
php -S localhost:8080 -d 'display_errors=1'
```
_**Tip:** You can scroll through previously typed commands in the Terminal using the up and down arrow keys_

You should see some output similar to the following:

```
[Sat Mar 7 14:15:10 2020] PHP 7.4.2 Development Server (http://localhost:8080) started
```

_**Tip:** when you want to stop the PHP webserver press `Ctrl + C`_

## Coding a Web Page

Ok let's get coding. Open up our `php` directory in your code editor. If you are using
the suggested Visual Studio Code editor you can do this by going to `File > Open Folder`
then selecting the `php` directory inside the `codebar` directory in your Home folder.
On Windows you'll find the directory at `Local Disk (C:) -> Users -> <your user> -> codebar`.

Open the `index.php` file in your editor.

PHP was designed to be included in files alongside HTML so when we
write PHP code it needs to be _between_ PHP start and end tags. The PHP
start tag looks like this `<?php` and the end tag looks like this `?>`.
Let's use `echo` to output some text.

```php
<p>Hello from HTML!</p>
<p><?php echo 'Hello from PHP!'; ?></p>
```

Don't forget the _statement terminator_ `;` otherwise PHP will throw an error.
Open up your web browser and navigate to [http://localhost:8080](http://localhost:8080)

Hello! 👋

Using PHP to output static content is a bit pointless so let's call one of the
built in PHP functions to output the date. Update the contents in your file to:

```php
<p>The date today is <?php echo date('D j M Y'); ?></p>
```

The `date()` function formats a date based on the special meaning of characters
in a string parameter. You can see the full list of options in the
[date function documentation](https://www.php.net/manual/en/function.date.php)

## The
