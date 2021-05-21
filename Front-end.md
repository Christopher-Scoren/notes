# Content
1. [Introduction](#Introduction)
2. [HTML](#HTML)  
  1.[Table](#table)  
  2.[Semantic HTML](#semantic-html)  
3. CSS


## Introduction
[Content](#content)

When a server responds to a client, the server specifies a status code as a part of the response.  
Status codes indicate whether or not the HTTP request was successfully completed and if there was an error, they contain some information about the type of error that happened.  
The status code helps the browser know how to handle the data that was sent back with the response.
![image](https://user-images.githubusercontent.com/55635400/118766617-5750b400-b885-11eb-80b1-fcfbd01ef716.png)

`CSS` stands for cascading style sheets

The internet has three basic parts:
* The last mile is the part of the internet that connects homes and small businesses to the internet.  
* Data centers are rooms full of servers that store user data and host online apps and content.  
* The backbone consists of long-distance networks — mostly on fiber optic cables — that carry data between data centers and consumers.  

[More about Internet](https://www.vox.com/2014/6/16/18076282/the-internet)

## HTML
[Content](#content)

![image](https://user-images.githubusercontent.com/55635400/118842364-cf44cb80-b8d1-11eb-92c4-bef4eaa3875d.png)

[html5-tag-cheat-sheet-2019.pdf](https://github.com/Christopher-SinCoren/notes/files/6513356/html5-tag-cheat-sheet-2019.pdf)

### class
```html
<p class="smth"></p>
<p class="one two three">this el has 3 classes</p>
```

### Table
[Content](#content)

![image](https://user-images.githubusercontent.com/55635400/118930267-356f3400-b94e-11eb-90d6-ea7be974f4fa.png)

We can use the scope attribute on `<th>` elements to indicate whether a `<th>` element is being used as a "row" heading or a "col" heading.

```html
<!DOCTYPE html>
<html>
<head>
  <title>Ship To It - Company Packing List</title>
  <link href="https://fonts.googleapis.com/css?family=Lato: 100,300,400,700|Luckiest+Guy|Oxygen:300,400" rel="stylesheet">
  <link href="style.css" type="text/css" rel="stylesheet">
</head>
<body>

  <ul class="navigation">
    <li><img src="https://content.codecademy.com/courses/web-101/unit-9/htmlcss1-img_logo-shiptoit.png" height="20px;"></li>
    <li class="active">Action List</li>
    <li>Profiles</li>
    <li>Settings</li>
  </ul>

  <div class="search">Search the table</div>
  
  <table>
    <thead>
    <tr>
      <th scope="col">Company Name</th>
      <th scope="col">Number of Items to Ship</th>
      <th scope="col">Next Action</th>
    </tr>
    </thead>
    <tbody>
      <tr>
        <td rowspan="2">Adam's Greenworks</td>
        <td>14</td>
        <td>Package Items</td>
      </tr>
      <tr>
    <td colspan="2">Send Invoice</td>
  </tr>
  <tr>
    <td>Baker's Bike Shop</td>
    <td>3</td>
    <td>Send Invoice</td>
  </tr>
  <tr>
    <td>Miss Sally's Southern</td>
    <td>4</td>
    <td>Ship</td>
  </tr>
  <tr>
    <td>Summit Resort Rentals</td>
    <td>4</td>
    <td>Ship</td>
  </tr>
  <tr>
    <td>Strike Fitness</td>
    <td>1</td>
    <td>Enter Order</td>
  </tr>
  </tbody>
  <tfoot>
    <td>Total</td>
    <td>28</td>
  </tfoot>
  </table>


</body>
</html>
  
```

### Semantic HTML
[Content](#content)

“Semantic HTML” refers to the idea that all your HTML markup should convey the underlying meaning of your content—not its appearance.  
SS
![image](https://user-images.githubusercontent.com/55635400/118932528-d101a400-b950-11eb-9550-0d0515cdf6a7.png)

The `<article>` element represents an independent article in a web page. It should only wrap content that can be plucked out of your page and distributed in a completely different context. For instance, an app like Flipboard should be able to grab an <article> element from your site, display it in its own app, and have it make perfect sense to its readers.

The `<section>` element is sort of like an `<article>`, except it doesn’t need to make sense outside the context of the document. That is, an app like Flipboard wouldn’t try to pull out all the `<section>`’s of your page and present them as independent pieces of content.

The `<nav>` element lets you mark up the various navigation sections of your website. This goes for the main site navigation, links to related pages in a sidebar, tables of content, and pretty much any group of links.

The `<header>` element is a new piece of semantic markup, not to be confused with headings (the `<h1>-<h6>` elements). It denotes introductory content for a section, article, or entire web page. “Introductory content” can be anything from your company’s logo to navigational aids or author information.  
![image](https://user-images.githubusercontent.com/55635400/118933254-a8c67500-b951-11eb-9e9f-0cb12c224499.png)

It’s a best practice to wrap a website’s name/logo and main navigation in a `<header>`.

Conceptually, `footers` are basically the same as headers, except they generally come at end of an article/website opposed to the beginning. Common use cases include things like copyright notices, footer navigation, and author bios at the end of blog posts.

Headers and footers are ways to add extra information to an article, but sometimes we want to remove information from an article. For example, a sponsored blog post might contain an advertisement about the sponsoring company; however, we probably don’t want to make it part of the article text. This is what the `<aside>` element is for.

The `<time>` element represents either a time of day or a calendar date. Providing a machine-readable date makes it possible for browsers to automatically link it to users’ calendars and helps search engines clearly identify specific dates.

The `<address>` element is like <time> in that it doesn’t deal with the overall structure of a document, but rather embellishes the parent <article> or `<body>` element with some metadata. It defines contact information for the author of the article or web page in question. `<address>` should not be used for arbitrary physical addresses.

the `<figure>` and `<figcaption>` elements. The former represents a self-contained “figure”, like a diagram, illustration, or even a code snippet. The latter is optional, and it associates a caption with its parent <figure> element.

A common use case for both of these is to add visible descriptions to the `<img/>` elements in an article

The `alt` attribute is closely related to the <figcaption> element. alt should serve as a text replacement for the image, while `<figcaption>` is a supporting description displayed with either the image or its text-based equivalent.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <link rel="stylesheet" type="text/css" href="style.css">
  </head>
  <body>
    <header>
      <h1>Navigational Links</h1>
      <nav>
        <ul>
          <li><a href="#home">Home</a></li>
          <li><a href="#posts">Posts</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
        
      </nav>
    </header>
    
    <main>
      <section>
        <article>
          <h2>Facts About Dogs</h2>
          <p>
          Dogs have a sense of time. It's been proven that they know the difference between a hour and five. If conditioned to, they can predict future events, such as regular walk times.
          </p>
          <p>There is a certain <i lang="fr" class="idiomatic">je ne sais quoi</i> in the air.</p>
        </article>
        <aside>
          <p>A study was conducted on dogs being away from their owners for varying hours and the studies show that dogs who were away from their owners the longest showed the greatest amount of affection!
          </p> 
        </aside>
      </section> 
      <figure>
        <img src="https://content.codecademy.com/courses/SemanticHTML/dogimage.jpeg"/>
        <figcaption>A cute dog.</figcaption>
      </figure>  
      <audio controls>
        <source src="https://content.codecademy.com/courses/SemanticHTML/dogBarking.mp3" type="audio/mp3">
      </audio> 
      <video src="https://content.codecademy.com/courses/SemanticHTML/dog-video.mp4" controls>
      </video>
      <embed src="https://content.codecademy.com/courses/SemanticHTML/dog-on-beach.gif"/>
         
    </main>
    
    <footer>
      <p>Contact me at +1 234 567 8910 </p>
    </footer>
              
  </body>
</html>
```
  
## CSS
  
![image](https://user-images.githubusercontent.com/55635400/119096309-1a6af580-ba1c-11eb-86aa-e85c9b10b91e.png)

### internal stylesheet
```html
  <head>
  <style>
    p {
      color: red;
      font-size: 20px;
    }
  </style>
</head>
```
  
### linking stylesheet
```html
<link href='https://www.codecademy.com/stylesheets/style.css' rel='stylesheet'>
```

### selectors types
```css
<!-- targeting all el-s -->
* {
  color: blue;
}

<!-- targeting all paragraphs -->
p {
  color: green;
}

<!-- targeting el-s with class="brand" -->
.brand {
 color: red;
}

<!-- targeting el-s with id="brand" -->
#brand {
  color: grey;
}

<!-- targeting el-s with some attribute -->
[href]{
   color: magenta;
}
```
And it can get more granular from there by adding type and/or attribute values. One way is by using type[attribute*=value]. In short, this code selects an element where the attribute contains any instance of the specified value. Let’s take a look at an example.
```html
<img src='/images/seasons/cold/winter.jpg'>
<img src='/images/seasons/warm/summer.jpg'>
```
```css
img[src*='winter'] {
  height: 50px;
}
 
img[src*='summer'] {
  height: 100px;
}
```
Factors such as user interaction, site navigation, and position in the DOM can all give elements a different state with pseudo-class.  
`:focus`, `:visited`, `:disabled`, and `:active` are all pseudo-classes.
A pseudo-class can be attached to any selector. It is always written as a colon : followed by a name. For example `p:hover`.
```css
p:hover {
  background-color: lime;
}
```

### Specificity
IDs are the most specific selector in CSS, followed by classes, and finally, type.  

### Chainning

```css
<!-- only the <h1> elements with a class of special -->
h1.special {
 
}
```
### Descendant Combinator
```html
<ul class='main-list'>
  <li> ... </li>
  <li> ... </li>
  <li> ... </li>
</ul>
```
```css
.main-list li {
 color: white;
}
```
### Multiple Selectors
```css
h1, 
.menu {
  font-family: Georgia;
}
```
### Visual rules

The `font-family` property defines the typeface of an element.
`font-size` controls the size of text displayed.
`font-weight` defines how thin or thick text is displayed.
The ` property places text in the left, right, or center of its parent container.
Text can have two different color attributes: `color` and `background-color`. color defines the color of the text, while background-color defines the color behind the text.
CSS can make an element transparent with the `opacity` property.
CSS can also set the background of an element to an image with the `background-image` property.
The `!important` flag will override any style, however it should almost never be used, as it is extremely difficult to override.

```css
h1 {
  font-family: Garamond;
  font-size: 18px;
   <!--  bold or normal  -->
  font-weight: bold; 
  text-align: right;
<!--  right \ left \ center \ justify  -->
  color: red;
  background-color: blue;
  opacity: 0.5;
  color: blue !important;
}
  .main-banner {
  background-image: url('https://www.example.com/image.jpg');
}
```
`justify`— spaces out text in order to align with the right and left side of the parent element.






















