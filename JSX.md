# Content

1. [Introduction](#Introduction)
2. [Rendering JSX](#Rendering-JSX)
3. [Virtual DOM](#Virtual-DOM)



## Introduction

`React.js` is a JavaScript library. It was developed by engineers at Facebook.  
`JSX` is a syntax extension for JavaScript. It was written to be used with React. before the file reaches a web browser, a JSX compiler will translate any JSX into regular JavaScript.  

A basic unit of JSX is called a JSX element.  
```
<h1>Hello world</h1>
```
This JSX element looks like HTML. The only difference is that it is in a JavaScript file, instead of in an HTML file.

JSX elements are treated as `JavaScript expressions`.  
JSX elements can have attributes, just like HTML elements can.

* A JSX attribute is written using HTML-like syntax: a name, followed by an equals sign, followed by a value. The value should be wrapped in quotes. A single JSX element can have many attributes.
```
my-attribute-name="my-attribute-value"
```
Here are some JSX elements with attributes:
```js
<a href='http://www.example.com'>Welcome to the Web</a>;
 
const title = <h1 id='title'>Introduction to React.js: Part I</h1>; 
```
* Nested JSX
```
<a href="https://www.example.com"><h1>Click me!</h1></a>
```
If a JSX expression takes up more than one line, then you must wrap the multi-line JSX expression in parentheses:
```
(
  <a href="https://www.example.com">
    <h1>
      Click me!
    </h1>
  </a>
)
//----
 const theExample = (
   <a href="https://www.example.com">
     <h1>
       Click me!
     </h1>
   </a>
 );
```
* a JSX expression must have exactly one outermost element.  
This works:
```
const paragraphs = (
  <div id="i-am-the-outermost-element">
    <p>I am a paragraph.</p>
    <p>I, too, am a paragraph.</p>
  </div>
);
```
And this doesn't:
```
const paragraphs = (
  <p>I am a paragraph.</p> 
  <p>I, too, am a paragraph.</p>
);
```

## Rendering JSX

The following code will render a JSX expression:
```js
ReactDOM.render(<h1>Hello world</h1>, document.getElementById('app'));
```

1. importing React libraries
```
import React from 'react';
import ReactDOM from 'react-dom';
```
`ReactDOM` is a JS library that contains several React-specific methods, all of which deal with the DOM.

ReactDOM.render() is the most common way to render JSX. It takes a JSX expression, creates a corresponding tree of DOM nodes, and adds that tree to the DOM. That is the way to make a JSX expression appear onscreen.

* ReactDOM.render()‘s first argument should evaluate to a JSX expression, it doesn’t have to literally be a JSX expression.

* One special thing about ReactDOM.render() is that it only updates DOM elements that have changed. That means that if you render the exact same thing twice in a row, the second render will do nothing.
```
const hello = <h1>Hello world</h1>;
 
// This will add "Hello world" to the screen:
 
ReactDOM.render(hello, document.getElementById('app'));
 
// This won't do anything at all:
 
ReactDOM.render(hello, document.getElementById('app'));
```

## Virtual DOM

A `virtual DOM object` is a representation of a DOM object, like a lightweight copy. A virtual DOM object has the same properties as a real DOM object, but it lacks the real thing’s power to directly change what’s on the screen.

When you render a JSX element, every single virtual DOM object gets updated.  
Once the virtual DOM has updated, then React compares the virtual DOM with a virtual DOM snapshot that was taken right before the update.  
By comparing the new virtual DOM with a pre-update version, React figures out exactly which virtual DOM objects have changed. This process is called “diffing.”  
Once React knows which virtual DOM objects have changed, then React updates those objects, and only those objects, on the real DOM.  

what happens when you try to update the DOM in React:

1. The entire virtual DOM gets updated.  
2. The virtual DOM gets compared to what it looked like before you updated it. React figures out which objects have changed.  
3. The changed objects, and the changed objects only, get updated on the real DOM.  
4. Changes on the real DOM cause the screen to change.  

