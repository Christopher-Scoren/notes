# Content

1.[Introduction](#Introduction)  
2.[NPM](#NPM)  
3.[Input and Output](#Input-and-Output)  
4.[Errors](#Errors)
5.[Filesystem](#Filesystem)


## Introduction

`Node.js` is a JavaScript runtime, or an environment that allows us to execute JavaScript code outside of the browser. A “runtime” converts code written in a high-level, human-readable, programming language and compiles it down to code the computer can execute.

`node -v` - check version

`REPL` is an abbreviation for read–eval–print loop. It’s a program that loops, or repeatedly cycles, through three different states: a read state where the program reads input from a user, the eval state where the program evaluates the user’s input, and the print state where the program prints out its evaluation to a console. Then it loops through these states again.

`node` command to access the REPL  
>A > character will show up in the terminal indicating the REPL is running and prompting your input. The Node REPL will evaluate your input line by line.  
`.editor` type it while in the REPL to access editor mode. => `ctrl + D` -> to launch the program

Every Node-specific global property sits inside the the Node global object.

`node JavaScriptCode.js` - to execute code from a file

`process.env` property is an object which stores and controls information about the environment in which the process is currently running.
>For example, the process.env object contains a PWD property which holds a string with the directory in which the current process is located.

We could store this information on the process.env. One convention is to add a property to process.env with the key NODE_ENV and a value of either production or development.
```js
if (process.env.NODE_ENV === 'development'){
  console.log('Testing! Testing! Does everything work?');
}
```
`process.memoryUsage()` returns information on the CPU demands of the current process. It returns a property that looks similar to this:
```js
{ rss: 26247168,
  heapTotal: 5767168,
  heapUsed: 3573032,
  external: 8772 }
```
`process.memoryUsage().heapUsed` will return a number representing how many bytes of memory the current process is using.

`process.argv` property holds an array of command line values provided when the current process was initiated. The first element in the array is the absolute path to Node, which ran the process. The second element in the array is the path to the file that’s running. The following elements will be any command line arguments provided when the process was initiated. Command line arguments are separated from one another with spaces.
```
node myProgram.js testing several features
```
The `core modules` are defined within Node.js’s source and are located in the lib/ folder. Core modules are required by passing a string with the name of the module into the `require()` function:
```js
// Require in the 'events' core module:
let events = require('events');
```
>The require() function will first check to see if its argument is a core module, if not, it will move on to different attempts to locate it. 

<hr/>

```js
// dog.js
module.exports = class Dog {
 
  constructor(name) {
    this.name = name;
  }
 
  praise() {
    return `Good dog, ${this.name}!`;
  }
};
```
Above, in the dog.js file, we assign the Dog class as the value of module.exports. Each JavaScript file in the Node environment has a special JavaScript object called module.exports. It holds everything in that file, or module, that’s available to be required into a different file.  
```js
// app.js
let Dog = require('./dog.js');
const tadpole = new Dog('Tadpole');
console.log(tadpole.praise());
```

## NPM

`NPM`, which stands for Node Package Manager, is an online collection, or registry, of software. Developers can share code they’ve written to the registry or download code provided by other developers.

When we download Node, the npm command-line tool is downloaded as well, which enables us to interact with the registry via our terminal.

Node provides an EventEmitter class which we can access by requiring in the events core module:
```js
// Require in the 'events' core module
let events = require('events');
 
// Create an instance of the EventEmitter class
let myEmitter = new events.EventEmitter();
```
Each `event emitter` instance has an `.on()` method which assigns a listener callback function to a named event. The .on() method takes as its first argument the name of the event as a string and, as its second argument, the listener callback function.

Each event emitter instance also has an .emit() method which announces a named event has occurred. The .emit() method takes as its first argument the name of the event as a string and, as its second argument, the data that should be passed into the listener callback function.
```js
let newUserListener = (data) => {
  console.log(`We have a new user: ${data}.`);
};
 
// Assign the newUserListener function as the listener callback for 'new user' events
myEmitter.on('new user', newUserListener)
 
// Emit a 'new user' event
myEmitter.emit('new user', 'Lily Pad') //newUserListener will be invoked with 'Lily Pad'
```
## Input and Output

In the Node environment, the console is the terminal, and the console.log() method is a “thin wrapper” on the `.stdout.write()` method of the process object. stdout stands for standard output.  

In Node, we can also receive input from a user through the terminal using the stdin.on() method on the process object:
```js
process.stdin.on('data', (userInput) => {
  let input = userInput.toString()
  console.log(input)
});
```
>Here, we were able to use .on() because under the hood process.stdin is an instance of EventEmitter. When a user enters text into the terminal and hits enter, a 'data' event will be fired and our anonymous listener callback will be invoked. 

The userInput we receive is an instance of the Node Buffer class, so we convert it to a string before printing.

## Errors

The Node environment has all the standard JavaScript errors such as `EvalError`, `SyntaxError`, `RangeError`, `ReferenceError`, `TypeError`, and `URIError` as well as the JavaScript Error class for creating new error instances.  

Within our own code, we can generate errors and throw them, and, with synchronous code in Node, we can use error handling techniques such as try...catch statements.

Many asynchronous Node APIs use error-first callback functions: callback functions which have an error as the first expected argument and the data as the second argument. If the asynchronous task results in an error, it will be passed in as the first argument to the callback function. If no error was thrown, the first argument will be undefined.
```js
const errorFirstCallback = (err, data)  => {
  if (err) {
    console.log(`There WAS an error: ${err}`);
  } else {
     // err was falsy
      console.log(`There was NO error. Event data: ${data}`);
  }
}
```
## Filesystem

This technique of isolating some applications from others is known as sandboxing. Sandboxing protects users from malicious programs and invasions of privacy.

In the back-end, however, less restricted interaction with the filesystem is essential. The Node `fs` core module is an API for interacting with the file system. It was modeled after the `POSIX` standard for interacting with the filesystem.

Each method available through the fs module has a synchronous version and an asynchronous version. 

One method available on the fs core module is the `.readFile()` method which reads data from a provided file:
```js
const fs = require('fs');
 
let readDataCallback = (err, data) => {
  if (err) {
    console.log(`Something went wrong: ${err}`);
  } else {
    console.log(`Provided file contained: ${data}`);
  }
};
 
fs.readFile('./file.txt', 'utf-8', readDataCallback);
```
>We invoked the .readFile() method with three arguments:  
>>The first argument is a string that contains a path to the file file.txt.  
>>The second argument is a string specifying the file’s character encoding (usually ‘utf-8’ for text files).  
>>The third argument is the callback function to be invoked when the asynchronous task of reading from the file system is complete. Node will pass the contents of file.txt into the provided callback as its second argument.  



















































