# Launching Node

## Overview

In this lesson, you'll learn how to run Node scripts with and without parameters.

## Objectives

1. Describe how to execute a Node script from a terminal
1. Use the node help command to get the list of node CLI commands
1. Use node CLI command options and flags to launch node scripts in different modes

## Describe how to execute a Node script from a terminal

So let's say you already wrote a Node script (even if you haven't). (A Node script is the same as a regular Node file containing JavaScript.) It can be as simple as a Hello World, for example we can use `console` interface:


```js
console.log('Hello World');
```

This code would be contained in a plain file with a `.js` extension, maybe `program.js`. How do you run it? Do you compile the code? Do you need an IDE (integrated development environment)? Where is the compiler? How long will it take to compile the program? Will it run on other platforms? If I compile it on Mac, will it work on Windows?

Please don't panic! Gladly, Node.js is an interpreted language. There's no compilation. There's no need for complex IDEs either (unless you like them). The `program.js` is a plain text file with a `.js` extension. To run this program, we go to terminal, *navigate to the folder with the script*, and run this command:

```
node program.js
```

Note: The `.js` extension in the command is optional, so `node program` will work as well.

If you are not in the same folder as your script file, you can navigate to it or specify path:

```js
node /Users/azat/Documents/Code/learn-co/program.js
```

The result will be `Hello World`.

## Use the node help command to get the list of node CLI commands

So what else can we do with the `node` command besides running our programs? What if you're an advanced Node developer and want to launch Node in different modes?

As most command-line interfaces (CLIs), Node has the help command which will show you usage, list of commands and options. As of version 5.1.0, when you run `node -h`, you'll get these:

* `-v`, `--version`: print Node.js version
* `-e`, `--eval script`: evaluate script
* `-p`, `--print`: evaluate script and print result
* `-c`, `--check`: syntax check script without executing
* `-i`, `--interactive`: always enter the REPL even if stdin does not appear to be a terminal
* `-r`, `--require`: module to preload (option can be repeated)
* `--no-deprecation`      silence deprecation warnings
* `--throw-deprecation`   throw an exception anytime a deprecated function is used
* `--trace-deprecation`   show stack traces on deprecations
* `--trace-sync-io`       show stack trace when use of sync IO is detected after the first tick
* `--track-heap-objects`  track heap object allocations for heap snapshots
* `--v8-options`          print v8 command line options
* `--tls-cipher-list=val` use an alternative default TLS cipher list
* `--icu-data-dir=dir`    set ICU data load path to dir (overrides NODE_ICU_DATA)

We'll ignore most of the options for now as they are for advanced developers. We just wanted to show you that they are there in case you want to poke around. Let's take a look at the first two to understand how to pass these options. The `-v` option prints the version, so we can use:

```
node -v
```

To get the version of Node installed.

Obviously, the commands and options will evolve with the future versions. It's good to know the current list by just typing `node --help`.

## Use node CLI command options and flags to launch node scripts in different modes

What if we don't want to run a file or save code to a file? You can run the code from a command-line. Just wrap it in double quotes and paste after the `-e` option. For example the following terminal command will print the date:

```
node -e "console.log(new Date)"
```

You might already guess the usage pattern. It looks like this:

```
node [options] [ -e script | script.js ] [arguments]
```

Where square brackets `[]` mean optional parameters. The `[options]` can be a single option like `-v`, or a combination of options listed by the help command. `script.js` is a file with the code to execute. We can also run code from a string (`-e`).

And the argument is the data to pass to the script. We can pass multiple argument separating them with spaces. For example, this code will print the third argument (index 2 because it's a 0-based array) back:

```
node -e "console.log(process.argv[2])" Azat "Pro Express.js"
Pro Express.js
```


---


<p data-visibility='hidden'>View <a href='https://learn.co/lessons/node-run-node' title='Launching Node'>Launching Node</a> on Learn.co and start learning to code for free.</p>

<p class='util--hide'>View <a href='https://learn.co/lessons/node-run-node'>Launching Node</a> on Learn.co and start learning to code for free.</p>
