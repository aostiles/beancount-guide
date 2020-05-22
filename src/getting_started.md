# What is Beancount?

Beancount is a plain-text accounting program. It's a way of keeping track of your finances in a text file.

The Beancount docs are at <http://furius.ca/beancount/doc/index>. I am not affiliated with Beancount and this document is not intended as a replacement for the Beancount docs.  

Rather, this document is just an opinionated guide for using Beancount. I have a quite simple financial situation, but hope this guide can grow.

## Why?

The biggest benefit I've gotten from using Beancount is _awareness_ of spending.

I like that Beancount forces me to think about where money is going. I like that, even if Beancount goes away, my text file is here to stay. I like the control Beancount gives me.

Some friends use spreadsheets. That probably works too, but I make mistakes. I like that Beancount makes sure my accounts balance.

# Installation

You'll need to use the command line to follow these instructions and interact with Beancount. On the mac, press `command + spacebar` and type in "terminal".

## Install Python 3

### Mac

```
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
$ brew install python
$ python --version
```

### Windows

<https://www.python.org/downloads/windows/>

## Install Beancount

```
pip3 install beancount
```

Install [Fava](https://beancount.github.io/fava/), a nice tool to help visualize your finances:

```
pip3 install fava
```

## Install Visual Studio Code

You'll need a text editor to edit your text file. You've probably used a text editor before. Windows comes with `Notepad` and the mac comes with `TextEdit`. Microsoft Word can also edit text files. However, these editors sometimes insert extra characters in text files.

Visual Studio Code works on all platforms and can be downloaded from <https://code.visualstudio.com/>.

## Install the VS Code Beanquick Extension

I wrote an extension for Visual Studio Code to help with manual data entry. It's not necessary, but I find it useful.

You can find the extension at <https://github.com/aostiles/Beanquick>.
