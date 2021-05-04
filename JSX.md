# Content

1. [Introduction](#Introduction)
2. [Rendering JSX](#Rendering-JSX)
3. [Virtual DOM](#Virtual-DOM)
4. [Difference btwn HTML and JSX](Difference-btwn-HTML-and-JSX)



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

## Difference btwn HTML and JSX

* class VS className

In JSX, you can’t use the word class! You have to use className instead:
```
<h1 className="big">Hey</h1>
```
* Self-Closing Tags
In JSX, you have to include the slash. If you write a self-closing tag in JSX and forget the slash, you will raise an error.
```
Fine in JSX:
  <br />
NOT FINE AT ALL in JSX:
  <br>
```
* curly braces
```
ReactDOM.render(
  <h1>2 + 3</h1>,
  document.getElementById('app')
);
// output: 2 + 3
```
This happened because 2 + 3 is located in between <h1> and </h1> tags. Any code in between the tags of a JSX element will be read as JSX, not as regular JavaScript! JSX doesn’t add numbers - it reads them as text, just like HTML.
```
...<h1>{2 + 3}</h1>...
output: 5
```
* variables in JSX
```
// Declare a variable:
const name = 'Gerdo';
 
// Access your variable 
// from inside of a JSX expression:
const greeting = <p>Hello, {name}!</p>;
```
* Variable Attributes in JSX
```
// Use a variable to set the `height` and `width` attributes:
 
const sideLength = "200px";
 
const panda = (
  <img 
    src="images/panda.jpg" 
    alt="panda" 
    height={sideLength} 
    width={sideLength} />
);
```
  * Object properties are also often used to set attributes:
```
const pics = {
  panda: "http://bit.ly/1Tqltv5",
  owl: "http://bit.ly/1XGtkM3",
  owlCat: "http://bit.ly/1Upbczi"
}; 
 
const panda = (
  <img 
    src={pics.panda} 
    alt="Lazy Panda" />
);
 
const owl = (
  <img 
    src={pics.owl} 
    alt="Unimpressed Owl" />
);
 
const owlCat = (
  <img 
    src={pics.owlCat} 
    alt="Ghastly Abomination" />
); 
```

* Event Listeners in JSX
```
<img onClick={myFunc} />
```
An event listener attribute’s name should be something like onClick or onMouseOver: the word on, plus the type of event that you’re listening for.  
An event listener attribute’s value should be a function.
```javascript
function myFunc() {
  alert('Make myFunc the pFunc... omg that was horrible i am so sorry');
}
 
<img onClick={myFunc} />
```
> `Note` that in HTML, event listener names are written in all lowercase, such as onclick or onmouseover. In JSX, event listener names are written in camelCase, such as onClick or onMouseOver.
 
* JSX Conditionals
It's impossible to inject an if statement into a JSX expression.  
This code will break:
```
(
  <h1>
    {
      if (purchase.complete) {
        'Thank you for placing an order!'
      }
    }
  </h1>
)
```
To resolve the problem:
```javascript
if (user.age >= drinkingAge) {
  message = (
    <h1>
      Hey, check out this alcoholic beverage!
    </h1>
  );
} else {
  message = (
    <h1>
      Hey, check out these earrings I got at Claire's!
    </h1>
  );
}
```
  * ternary operator
```
const headline = (
  <h1>
    { age >= drinkingAge ? 'Buy Drink' : 'Do Teen Stuff' }
  </h1>
);
```
  * &&
&& works in conditionals that will sometimes do an action, but other times do nothing at all.
```
const tasty = (
  <ul>
    <li>Applesauce</li>
    { !baby && <li>Pizza</li> }
    { age > 15 && <li>Brussels Sprouts</li> }
    { age > 20 && <li>Oysters</li> }
    { age > 25 && <li>Grappa</li> }
  </ul>
);
```
>If the expression on the left of the && evaluates as true, then the JSX on the right of the && will be rendered. If the first expression is false, however, then the JSX to the right of the && will be ignored and not rendered.

* .map in JSX
If you want to create a list of JSX elements, then .map() is often your best bet.
```
const strings = ['Home', 'Shop', 'About Me'];
const listItems = strings.map(string => <li>{string}</li>);
<ul>{listItems}</ul>
```
```
// This is fine in JSX, not in an explicit array:
 
<ul>
  <li>item 1</li>
  <li>item 2</li>
  <li>item 3</li>
</ul>
 
// This is also fine!
 
const liArray = [
  <li>item 1</li>, 
  <li>item 2<li>, 
  <li>item 3</li>
];
 
<ul>{liArray}</ul>
```
* Keys

A key is a JSX attribute. The attribute’s name is key. The attribute’s value should be something unique, similar to an id attribute.  
keys don’t do anything that you can see! React uses them internally to keep track of lists. If you don’t use keys when you’re supposed to, React might accidentally scramble your list-items into the wrong order.
```
<ul>
  <li key="li-01">Example1</li>
  <li key="li-02">Example2</li>
  <li key="li-03">Example3</li>
</ul>
```
Not all lists need to have keys. A list needs keys if either of the following are true:

  * The list-items have memory from one render to the next. For instance, when a to-do list renders, each item must “remember” whether it was checked off. The items shouldn’t get amnesia when they render.  
  * A list’s order might be shuffled. For instance, a list of search results might be shuffled from one render to the next.

* React.createElement
You can write React code without using JSX at all!
```
//JSX written
const h1 = <h1>Hello world</h1>;

//React without JSX
const h1 = React.createElement(
  "h1",
  null,
  "Hello, world"
);
```
> When a JSX element is compiled, the compiler transforms the JSX element into the method that you see above: React.createElement(). Every JSX element is secretly a call to React.createElement().


