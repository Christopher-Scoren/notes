# Content

1.[Introduction](#Introduction)
2.[NPM](#NPM)


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























