---
layout: page
title: Installation guide
---

Welcome! Before we start learning to make web pages with PHP we need to get a few things installed if they aren't already:

- **PHP**
- **Composer** a 'dependency manager' for PHP which lets you install tools and libraries written by the PHP community
- **PsySH** a really useful type of tool called a REPL\* which lets you type in pieces of PHP code and see the result

_\*REPL: Read Evaluate Print Loop_

In order to do that we need to install some dependencies based on your operating
system.

## MacOS

For these steps and the tutorials you'll need to use the Terminal app which is
installed on all Macs. Use Spotlight (MacOS search) and type in 'Terminal.app'
to find and open it. We'll refer to this as the Terminal from now on.

1. Install the XCode Command Line Tools if you haven't before by typing
   `xcode-select --install` in the Terminal and pressing return
2. Install [Homebrew](https://brew.sh/) the excellent MacOS package manager
   by following the linked instructions

Great job! 🔥 You're all set to [install PHP](#installing-php)

## Windows

The PHP tutorials require Windows 10 so that we can install the Windows
Subsystem for Linux (WSL). This is a fantastic feature from Microsoft
allowing users to run a Linux environment inside Windows to make web
development much easier.

1. Follow the [instructions](https://docs.microsoft.com/en-us/windows/wsl/install-win10)
   to enable WSL and install the **Ubuntu** (18.04) Linux distribution
   in the Microsoft Store
2. Open up the Ubuntu app (use Windows search to find it)
   and after the initial setup has run follow the instructions to create your
   admin (sudo) account. We'll refer to this interface as the Terminal from now on
3. Type `sudo apt-get update` in your Terminal and press return to update all the Ubuntu
   code packages which will take a few minutes. Using `sudo` at the start is similar to
   running as Administrator on Windows and you'll be asked for the password you entered
   in step 2. Be very careful when running commands with `sudo` as Linux will trust you
   know what you're doing and allow you to make system level changes without safety checks

Nice work you're running Ubuntu! 💃 Now follow the [Linux](#linux) instructions
in the next section 👇 to get Homebrew installed using your Terminal.

## Linux

Linux is a free and open source operating system used by many developers to
build web software as the majority of the world's webservers run on Linux.
The Linux Terminal is very similar to the MacOS Terminal.

Different flavours of Linux called 'distributions' have their own
way of managing code packages. To keep things consistent we will use
Homebrew to install PHP for these beginner tutorials. You can always
uninstall it later and use your distribution's PHP packages if you move on
to more advanced Linux usage.

You'll need to open the Terminal app and follow the instructions below. If you
just installed Windows Subsystem for Linux (above) then follow instructions
for the **Ubuntu** distribution.

1. Paste the commands for your distribution in the
   [Linux/WSL Requirements](https://docs.brew.sh/Homebrew-on-Linux#linuxwsl-requirements)
   section into your Terminal and press return to install Homebrew's dependencies
2. Now install Homebrew for Linux by following the [Install](https://docs.brew.sh/Homebrew-on-Linux#install)
   section. Don't worry if you see the message `Warning: /home/linuxbrew/.linuxbrew/bin is not in your PATH`
   just be sure to run the second set of commands in the Install section which sort this out

Great job! ⚡ You're all set to [install PHP](#installing-php)

## Installing PHP

You might already have PHP installed. In the Terminal type `which php` and press enter.
If you see something like `PHP 7.4.3 (cli) (built: Feb 23 2020 07:24:48) ( NTS )` then
it is already installed and you can _start from 3_.

1. In the Terminal type `brew install php` then press return to install the latest
   PHP using Homebrew (this can take around 5-10 minutes to complete)
2. Close / reopen the Terminal and type `php --version` then press return. The version
   of PHP displayed should be greater than or equal to 7.4 🙌
3. Type `brew install composer` in your Terminal then press return to install Composer
   &ndash; PHP's code library manager
4. Paste `composer global require psy/psysh:@stable` in your Terminal and press return to install the [PsySH](https://psysh.org/) **R**ead **E**val **P**rint **L**oop (REPL)
5. Paste the following into your terminal and press return. These tell your Terminal where composer lives:
   ```
   test -r ~/.bashrc && echo 'PATH=$PATH:~/.config/composer/vendor/bin' >> ~/.bashrc
   test -r ~/.zshrc && echo 'PATH=$PATH:~/.config/composer/vendor/bin' >> ~/.zshrc
   ```
   Chat to your coach if you'd like a more in-depth explanation 😊
6. Finally close and reopen the Terminal app then type `psysh --version` and press return. You should see something similar to this `Psy Shell v0.9.12 (PHP 7.4.2 — cli)`

🎉 You're all done! Head over to the [first tutorial](/php/lesson1/tutorial.html).
