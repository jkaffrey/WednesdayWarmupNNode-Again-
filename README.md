# Intro to Node (again)

## Objectives

By the end of this article you will be able to:

- Understand what APIs Node comes with and how they differ from the ones a web browser offers.
- Be able to use the REPL
- Be able to explain the history of Node and why it is so useful.

## What is Node.js

Node.js is a powerful server-side platform for executing JavaScript. In particular, its largest advantage over the "plain old" JavaScript language is that it provides access to the filesystem and network. Another way to think about this, is that Node.js is just another environment that can run JavaScript code (the Chrome Web Console is another example). The key distinction with Node.js is that it is not the browser (client), there is no DOM nor `window`; those are browser concepts. Node.js is on the other side of the coin; the server. This concept will be further explored when using Node.js in the context of the web, for now knowing this basic conceptualization is sufficient.

Some of the largest [companies on the planet use Node.js](https://github.com/joyent/node/wiki/projects,-applications,-and-companies-using-node) including eBay, Joyent, Klout, LinkedIn, Microsoft, and PayPal use Node.js for some part of their stack. Depending on the firm, usage may vary widely, but it is highly unlikely that any of these companies operate entirely (or even majority) in Node.js. Node.js is like anything else though, and has its [disadvantages](http://www.quora.com/What-are-the-disadvantages-of-using-Node-js) and [advantages](http://www.toptal.com/nodejs/why-the-hell-would-i-use-node-js).

Node.js is important because it is a JavaScript _runtime_ for the server. A [runtime](https://en.wikipedia.org/wiki/Runtime_system) is the code that is dynamically executed during program operation. Javascript is an interpreted language, which means that it isn't compiled prior to running. C++, Objective-C and many other languages not based on C are put through a "compiler" that turns them into instructions that can be directly sent to the processor to be executed. An interpreted language is not compiled before it runs, but is instead compiled Just In Time (often abbreviated JIT) when the actual code is about to be run.

One of the biggest changes that the V8 runtime introduces is in it's JIT compiler. It dynamically compiles and optimizes Javascript as it runs, and re-optimizes it according to the state of the program as the program runs. [Read the wikipedia entry on V8](https://en.wikipedia.org/wiki/V8_(JavaScript_engine)).

- _Challenge_: Explain what it means to say that [V8](https://developers.google.com/v8/?hl=en) provides the runtime environment for JavaScript on the server.
- What is the runtime in Chrome? In Firefox?

One powerful feature of Node.js is the _REPL_; Read, Eval, Print, Loop. This is the `node` console, commands may be entered to be evaluated and their results will be shown (if they emit any).

### API

Just like the browser supplies us with `window`, `console` and `document` APIs, Node provides a set of global objects for us to use.

**You Do:**

- Take a minute to look over the globals that node provides [here](https://nodejs.org/api/globals.html).
- Does node provide objects that are the same as what the browser provides?


### REPL

**Open your terminal**, and type `node`, and hit enter. You should see a `>` appear, and it is in this mode you can enter any valid javascript and it will interpret it. It's similar to the console you're used to from the browser, only we don't have access to `document` or any other browser APIs.

Now, `touch` a new javascript file in a new folder in your projects or `src` directory. Call it `script.js`.<br>
`touch ~/src/node/examples/script.js` (you can use your own folder structure if you like)

Open that file in your IDE, and put the following code in:

```javascript
console.log("Hello World");
```

Now `cd` into that folder and run that file with `node script.js`. This is how we execute files with the `node` runtime.

## NPM & Modules

What is [npm](https://en.wikipedia.org/wiki/Npm_(software))? `npm` is a package manager for Node.js and JavaScript. _Packages_, or _libraries_, are bits of code that are available for reuse.

One of the best features of Node.js is that it is _lightweight_; that is, Node itself provides minimal functionality. Most things are done with _modules_. NPM packages are an example of [Modules](https://en.wikipedia.org/wiki/Modular_programming), which is a concept we see across many languages and frameworks.

An important consequence of the Node.js module system is that there is not a single _global scope_, in fact, each file defines its own scope, and then modules are _composed_ together into other modules.

There are three types of modules in node.

 - Core modules: modules that come with Node.
 - NPM modules: modules installed with NPM.
 - Local modules: modules you wrote.

Example:

```javascript
// require core module
var fs = require('fs');

//require npm module
var express = require('express');

//require local module
var util = require('./path/to/util');
```

You can look at [Nodes Docs](https://nodejs.org/api/index.html) for a complete list of what modules Node provides. A few notable ones would be:

- FS
- HTTP
- Path

In addition, you can search [NPM](https://www.npmjs.com/) to find modules that others have written.

## Exercises

- [CSV to Markdown](https://github.com/gSchool/csv-to-markdown-js)

## Resources

- [Node Docs](https://nodejs.org/dist/latest-v6.x/docs/api/)
- [EJS: Node](http://eloquentjavascript.net/20_node.html)
- [Learn You Node](https://github.com/workshopper/learnyounode)
- [What is Node.js](https://www.youtube.com/watch?v=pU9Q6oiQNd0)

## Tangental Resources

- [V8](https://en.wikipedia.org/wiki/V8_%28JavaScript_engine%29)
- [Event Driven Programming](https://en.wikipedia.org/wiki/V8_%28JavaScript_engine%29)

# File System

## Objectives

By the end of this article you should be able to:

- Require and use FS in a project and use it to:
  - Read files
  - Write files
  - Append to files

## File System Module (FS)

FS is a module that allows you to interact with the file system. It can be used to read, write, append, modify and delete files among many other tasks.

**You Do**: What do you think you would use FS for?

FS is a core Node module, meaning it can be required in any project:

```javascript
var fs = require('fs');
```

It provides both synchronous and aysnchronous methods. For example, `writeSync` is the synchronous version of `write`.

**You Do**: Why would we want both an asynchronous and a synchronous way to accomplish the same thing?


## Exercises

- [CLI TODO App](https://github.com/gSchool/node-fs-todo-cli-example)
- [FS Exercise](https://github.com/gSchool/node_fsModule)
- [Log Parsing](https://github.com/gSchool/js-node-log-file-parsing)

Stretch:

- [Log Parsing Pt. 2: Writing an Interpreter](https://github.com/gSchool/node-async-text-parsing-0)

## Resources

- [Node Docs](https://nodejs.org/dist/latest-v6.x/docs/api/fs.html#fs_file_system)
# WednesdayWarmupNNode-Again-
