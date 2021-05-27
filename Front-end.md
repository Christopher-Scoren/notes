# Content
1. [Introduction](#Introduction)
2. [HTML](#HTML)  
  1.[Table](#table)  
  2.[Semantic HTML](#semantic-html)  
3. [CSS](#css)  
  1.[Typography](#typography)  
  2.[Box Model](#box-model)  
  3.[Display and Positioning](#Display-and-Positioning)  
  4.[Color wheel](#color-wheel)  
  5.Links and buttons  
  6.[Secondary navigation](#secondary-navigation)  
  7.[Responsive Design](#responsive-design)  


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

The `<article>` element represents an independent article in a web page. It should only wrap content that can be plucked out of your page and distributed in a completely different context. For instance, an app like Flipboard should be able to grab an `<article>` element from your site, display it in its own app, and have it make perfect sense to its readers.

The `<section>` element is sort of like an `<article>`, except it doesn’t need to make sense outside the context of the document. That is, an app like Flipboard wouldn’t try to pull out all the `<section>`’s of your page and present them as independent pieces of content.

The `<nav>` element lets you mark up the various navigation sections of your website. This goes for the main site navigation, links to related pages in a sidebar, tables of content, and pretty much any group of links.

The `<header>` element is a new piece of semantic markup, not to be confused with headings (the `<h1>-<h6>` elements). It denotes introductory content for a section, article, or entire web page. “Introductory content” can be anything from your company’s logo to navigational aids or author information.  
![image](https://user-images.githubusercontent.com/55635400/118933254-a8c67500-b951-11eb-9e9f-0cb12c224499.png)

It’s a best practice to wrap a website’s name/logo and main navigation in a `<header>`.

Conceptually, `footers` are basically the same as headers, except they generally come at end of an article/website opposed to the beginning. Common use cases include things like copyright notices, footer navigation, and author bios at the end of blog posts.

Headers and footers are ways to add extra information to an article, but sometimes we want to remove information from an article. For example, a sponsored blog post might contain an advertisement about the sponsoring company; however, we probably don’t want to make it part of the article text. This is what the `<aside>` element is for.

The `<time>` element represents either a time of day or a calendar date. Providing a machine-readable date makes it possible for browsers to automatically link it to users’ calendars and helps search engines clearly identify specific dates.

The `<address>` element is like `<time>` in that it doesn’t deal with the overall structure of a document, but rather embellishes the parent `<article>` or `<body>` element with some metadata. It defines contact information for the author of the article or web page in question. `<address>` should not be used for arbitrary physical addresses.

the `<figure>` and `<figcaption>` elements. The former represents a self-contained “figure”, like a diagram, illustration, or even a code snippet. The latter is optional, and it associates a caption with its parent `<figure>` element.

A common use case for both of these is to add visible descriptions to the `<img/>` elements in an article

The `alt` attribute is closely related to the `<figcaption>` element. alt should serve as a text replacement for the image, while `<figcaption>` is a supporting description displayed with either the image or its text-based equivalent.

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


### Typography
![image](https://user-images.githubusercontent.com/55635400/119250280-a198a480-bba7-11eb-8b85-c63be7cb8c39.png)  
![image](https://user-images.githubusercontent.com/55635400/119250390-75315800-bba8-11eb-9e98-fe6277d2ae60.png)

<!--  -->
```css
p {
  font-family: Roboto;
  font-family: 'Times New Roman';
  font-family: Caslon, Georgia, 'Times New Roman'; <!-- first 2 fonts aren't available then TNR works (most devices have it)-->
  font-family: Caslon, Georgia, 'Times New Roman', serif; <!-- first 3 fonts aren't available -->
  
  font-weight: bold; <!-- normal \ bolder \ lighter-->
  font-weight: 100; <!-- from 1 to 1000 tho preferably with 100 step-->
  
   font-style: italic; <!-- \ normal -->
   text-transform: uppercase; <!-- \ lowercase -->
  
   <!-- TEXT LAYOUT -->
  letter-spacing: 2px;
  word-spacing: 0.3em;
  
  line-height: 1.4; <!-- how tall we want each line containing our text to be -->
  
  text-align: right; <!-- \ center \ left \ justify \ start \ end -->
}
```
Downloading and adding fonts

When you’re done selecting a font and its styles, you can review your selected font family, and a <link> element will be automatically generated for you to use on your site!

* 1st variant
```html
<head>
  <!-- Add the link element for Google Fonts along with other metadata -->
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@100&display=swap" rel="stylesheet">
<head>
```
```css  
p {
  font-family: 'Roboto', sans-serif;
}
```
* 2nd variant

fonts formats
  
  *OTF (OpenType Font)
  *TTF (TrueType Font)
  *WOFF (Web Open Font Format)
  *WOFF2 (Web Open Font Format 2)

The different formats are a progression of standards for how fonts will work with different browsers, with WOFF2 being the most progressive. It’s a good idea to include TTF, WOFF, and WOFF2 formats with your @font-face rule to ensure compatibility on all browsers.

Download -> move them to a folder inside your website’s working directory -> css rule:
```css
@font-face {
  font-family: 'MyParagraphFont';
  src: url('fonts/Roboto.woff2') format('woff2'),
       url('fonts/Roboto.woff') format('woff'),
       url('fonts/Roboto.ttf') format('truetype');
}
```

### Box model

![image](https://user-images.githubusercontent.com/55635400/119305827-ebe65800-bc71-11eb-8d84-7cb9b17f97ee.png)  
![image](https://user-images.githubusercontent.com/55635400/119307098-d114e300-bc73-11eb-94a4-4e4c49b17f75.png)


```css
p {
  height: 80px;
  width: 240px;
  
  border: 3px solid coral; <!-- 3px / thin / medium / thick || none \ dotted \ solid \ etc || any -->
  border-radius: 5px; <!-- / 50% \\set all four corners.  -->
  
  padding: 10px; <!-- + padding-top -right -bottom -left -->
  padding: 6px 11px 4px 9px; <!-- all 4: top right bottom left -->
  padding: 5px 10px 20px; <!-- 1st sets -top value (5px), 2nd sets the -left and -right values (10px), and 3rd sets the -bottom value (20px). -->
  padding: 5px 10px; <!-- top+bottom and right+left -->
  
  margin: 20px; <!-- + margin-top -right -bottom -left -->
  margin: 6px 10px 5px 12px;
  margin: 5px 12px 4px;
  margin: 20px 10px;
  
  <!-- to center with margin: -->
  width: 400px; <!-- iportant to set width -->
  margin: 0 auto;
  
  min-width: 300px;
  max-width: 600px;
  
  min-height: 150px;
  max-height: 300px;
  
  overflow: hidden; <!-- scroll / visible -->
  
  visibility: hidden; <!-- visible \ collapse -->
}

  <!-- resetting defaults -->

* {
  margin: 0;
  padding: 0;
}
```
* The default border is medium none color, where color is the current color of the element. If width, style, or color are not set in the CSS file, the web browser assigns the default value for that property.

*  What’s the difference between display: none and visibility: hidden? An element with display: none will be completely removed from the web page. An element with visibility: hidden, however, will not be visible on the web page, but the space reserved for it will.
<!--  -->

#### Content box
![image](https://user-images.githubusercontent.com/55635400/119307836-f3f3c700-bc74-11eb-989d-709b8049ed3b.png)
In CSS, the `box-sizing` property controls the type of box model the browser should use when interpreting a web page. The default value of this property is `content-box`.

#### Border box
![image](https://user-images.githubusercontent.com/55635400/119308010-2dc4cd80-bc75-11eb-9fa3-e05cadf92045.png)
```css
* {
  box-sizing: border-box;
}
```
In this box model, the height and width of the box will remain fixed. The border thickness and padding will be included inside of the box, which means the overall dimensions of the box do not change.

### Display and Positioning

`Block-level elements` like these boxes create a block the full width of their parent elements, and they prevent other elements from appearing in the same horizontal space. This is the default position for block-level elements.

```css
p {
  position:static; //relative / fixed / absolute / stiky
}
```

#### Position Relative

This value allows you to position an element relative to its default static position on the web page.
```css
.green-box {
  background-color: green;
  position: relative;
  top: 50px;
  left: 120px;
}
```
![image](https://user-images.githubusercontent.com/55635400/119310001-d2e0a580-bc77-11eb-94f0-ea108417d811.png)

#### Position: Absolute

When an element’s position is set to absolute, all other elements on the page will ignore the element and act like it is not present on the page. The element will be positioned relative to its closest positioned parent element, while offset properties can be used to determine the final position from there.
![image](https://user-images.githubusercontent.com/55635400/119310115-fc99cc80-bc77-11eb-9bec-432a95e63f42.png)
> The “Website building in progress. Please come back later!” text is displaced from its static position at the top left corner of its parent container. It has offset property declarations of top: 300px; and right: 0;, positioning it 300 pixels down, and 0 pixels from the right side of the page.

When an element’s position is set to absolute, as in the last exercise, the element will scroll with the rest of the document when a user scrolls.

#### Position: Fixed
```css
.title {
  position: fixed;
  top: 0px;
  left: 0px;
}
```
In the example above, the .title element will remain fixed to its position no matter where the user scrolls on the page.
![image](https://user-images.githubusercontent.com/55635400/119310349-48e50c80-bc78-11eb-9350-5b23242fb385.png)


#### Position: Sticky

The sticky value is another position value that keeps an element in the document flow as the user scrolls, but sticks to a specified position as the page is scrolled further.
```css
.box-bottom {
  background-color: darkgreen;
  position: sticky;
  top: 240px;
}
```
![image](https://user-images.githubusercontent.com/55635400/119310473-7631ba80-bc78-11eb-80b1-e5cb18b3f97f.png)

#### z-index

The z-index property controls how far back or how far forward an element should appear on the web page when elements overlap. This can be thought of as the depth of elements, with deeper elements appearing behind shallower elements.

* Default static positioned elements will ignore z-index.
```css
.blue-box {
  background-color: blue;
  position: relative;
  z-index: 1;
}
 
.green-box {
  background-color: green;
  position: relative;
  top: -170px;
  left: 170px;
}
```
![image](https://user-images.githubusercontent.com/55635400/119310582-9a8d9700-bc78-11eb-8f91-a7847edf7375.png)

#### inline display

 `Inline elements` have a box that wraps tightly around their content, only taking up the amount of space necessary to display their content and not requiring a new line after each element. The height and width of these elements cannot be specified in the CSS document. 

The CSS `display` property provides the ability to make any element an inline element. This includes elements that are not inline by default such as paragraphs, divs, and headings.

```css
h1 {
  display: inline; //block / inline-block
}
```
Some elements are not displayed in the same line as the content around them. These are called `block-level` elements. These elements fill the entire width of the page by default, but their width property can also be set. Unless otherwise specified, they are the height necessary to accommodate their content.

`Inline-block` display combines features of both inline and block elements. Inline-block elements can appear next to each other and we can specify their dimensions using the width and height properties. Images are the best example of default inline-block elements.


#### float

The float property is commonly used for wrapping text around an image while moving elements left and right for layout purposes is better left to tools like CSS grid and flexbox.

```css
float: left; //right
```

#### clear

The float property can also be used to float multiple elements at once. However, when multiple floated elements have different heights, it can affect their layout on the page. Specifically, elements can “bump” into each other and not allow other elements to properly move to the left or right.

The `clear` property specifies how elements should behave when they bump into each other on the page.  
* left—the left side of the element will not touch any other element within the same containing element.  
* right—the right side of the element will not touch any other element within the same containing element.  
* both—neither side of the element will touch any other element within the same containing element.  
* none—the element can touch either side.  

### Color wheel

![image](https://user-images.githubusercontent.com/55635400/119450333-68de0400-bd3c-11eb-8c9c-d2db9fb10362.png)

![image](https://user-images.githubusercontent.com/55635400/119452810-73e66380-bd3f-11eb-9762-0fce96fba022.png)


* The “pure” color is set with the Hue. This is expressed as the angle in degrees around the color wheel.  
* Saturation refers to the intensity or purity of that hue. Colors with full saturation (100%) are the color itself, colors with no saturation (0%) are completely grayscale.  
* Lightness refers to the lightness of the color. 0% is black, 100% is white.  
* A, or alpha, refers to the opacity. 0% is fully transparent, 100% is fully opaque.  

`Warm colors` range between red and yellow, which include various versions of those colors in addition to orange. This also comprises colors such as brown and tan. 
 in contrast to `warm colors`, there are colors that are considered to be “cool”. These colors range between blue, purple and green. Most gray colors fall into the cool category as well.  

#### color schemes

![image](https://user-images.githubusercontent.com/55635400/119451293-bdce4a00-bd3d-11eb-801b-ec34ca2fcfdf.png)

### Links and buttons

 CSS pseudo-classes: `:link`, `:visited`, `:hover`, `:active` 
```css

```

`Skeuomorphism` is a term most often used in graphical user interface design to describe interface objects that mimic their real-world counterparts in how they appear and/or how the user can interact with them. A well-known example is the recycle bin icon used for discarding files.

 to implement a bare minimum 3-D button design, the following CSS ruleset could be used:
```css
.button {
  padding: 5px;
  border: 1px solid black;
  border-radius: 5px;
  text-decoration: none;
  box-shadow: 0px 5px;
}
 
.button:hover {
  cursor: pointer;
}
 
.button:active {
  margin-top: 5px;
  color: black;
  box-shadow: 0px 0px;
}
```

### Secondary navigation

The `primary navigation system` typically contains the most important links and buttons that need to be displayed on every single page of the site.

`Secondary navigation`, or breadcrumb navigation, usually consists of a clickable list of pages or attributes that led to the current page. It can help users understand the extent of the site and also where they are currently.

For example, a shopping site may have a breadcrumb trail leading to a pair of shoes like so:
![image](https://user-images.githubusercontent.com/55635400/119659282-af178e00-be36-11eb-9237-d922ecb02519.png)

```css
.breadcrumb li+li::before {
	padding: 10px;
  content: ">";
}
```
>* The + is called the adjacent sibling combinator; it will only select two li‘s when they are immediately next to each other, with the same parent. The element that actually gets selected is the second element of this sibling pair.  
>* The ::before part of this selector creates a pseudo-element. The ::before pseudo-element is often used with the content property, to add content that will be displayed just before the selected element.

![image](https://user-images.githubusercontent.com/55635400/119662231-d4f26200-be39-11eb-8863-37393d313113.png)

```css
.breadcrumb {
  text-align: left;
}
.breadcrumb li {
  float: left;
}

.breadcrumb a {
  color: #fff;
  background: darkcyan;
  text-decoration: none;
  position: relative;
  height: 30px;
  line-height: 30px;
  text-align: center;
  margin-right: 15px;
  padding: 0 5px;
}

.breadcrumb a::before,
.breadcrumb a::after {
  content: "";
  position: absolute;
  border-color: darkcyan;
  border-style: solid;
  border-width: 15px 5px;
}

.breadcrumb a::before {
  left: -10px;
  border-left-color: transparent;
}
.breadcrumb a::after {
  left: 100%;
  border-color: transparent;
  border-left-color: darkcyan;
}

.breadcrumb a:hover {
  background-color: blue;
}
.breadcrumb a:hover::before {
  border-color: blue;
  border-left-color: transparent;
}
.breadcrumb a:hover::after {
  border-left-color: blue;
}
```

There are three major types of breadcrumbs:

* Location
* Attribute
* Path

### Responsive design

#### Relative measurements

Responsive design refers to the ability of a website to resize and reorganize its content based on:

* The size of other content on the website.
* The size of the screen the website is being viewed on.

`em` - represents the font-size of the current element or the default base font-size set by the browser if none is given. For example, if the base font of a browser is 16 pixels (which is normally the default size of text in a browser), then 1 em is equal to 16 pixels. 2 ems would equal 32 pixels, and so on.
>Historically, the em represented the width of a capital letter M in the typeface and size being used. That is no longer the case.
```css
.heading {
  font-size: 2em;
}
```
>In the example above, no base font has been specified, therefore the font size of the heading element will be set relative to the default font size of the browser. Assuming the default font size is 16 pixels, then the font size of the heading element will be 32 pixels.

```css
.splash-section {
  font-size: 18px;
}
 
.splash-section h1 {
  font-size: 1.5em;
}
```
>The example above shows how to use ems without relying on the default font size of the browser. Instead, a base font size (18px) is defined for all text within the splash-section element.

`rem` - Rem stands for root em. It acts similar to em, but instead of checking parent elements to size font, it checks the root element. The root element is the `<html>` tag.
>Most browsers set the font size of `<html>` to 16 pixels, so by default rem measurements will be compared to that value. 

To set a different font size for the root element:
```css
html {
  font-size: 20px;
}
 
h1 {
  font-size: 2rem;
}
```
>One advantage of using rems is that all elements are compared to the same font size value, making it easy to predict how large or small font will appear. 
>>If you are interested in sizing elements consistently across an entire website, the rem measurement is the best unit for the job.   
>>If you’re interested in sizing elements in comparison to other elements nearby, then the em unit would be better suited for the job.

`%`

`%` - Percentages are often used to size box-model values, like width and height, padding, border, and margins. They can also be used to set positioning properties (top, bottom, left, right).
```css
.main {
  height: 300px;
  width: 500px;
}
 
.main .subsection {
  height: 50%;
  width: 50%;
}
```
>When percentages are used, elements are sized relative to the dimensions of their parent element (also known as a container). Therefore, the dimensions of the .subsection div will be 150 pixels tall and 250 pixels wide. Be careful, a child element’s dimensions may be set erroneously if the dimensions of its parent element aren’t set first.

>Because the box model includes padding, borders, and margins, setting an element’s width to 100% may cause content to overflow its parent container. While tempting, 100% should only be used when content will not have padding, border, or margin.

!

When percentages are used to set padding and margin, however, they are calculated based only on the width of the parent element.  
For example, when a property like margin-left is set using a percentage (say 50%), the element will be moved halfway to the right in the parent container (as opposed to the child element receiving a margin half of its parent’s margin).

Vertical padding and margin are also calculated based on the width of the parent.

* When height and width are set using percentages, you learned that the dimensions of child elements are calculated based on the dimensions of the parent element.

* When percentages are used to set padding and margin, however, they are calculated based only on the width of the parent element.

 * When using relative sizing, ems and rems should be used to size text and dimensions on the page related to text size (i.e. padding around text). This creates a consistent layout based on text size. Otherwise, percentages should be used.

#### Scalling images and videos

```css
.container {
  width: 50%;
  height: 200px;
  overflow: hidden;
}
 
.container img {
  max-width: 100%;
  height: auto;
  display: block;
}
```
>In the example above, .container represents a container div. It is set to a width of 50% (half of the browser’s width, in this example) and a height of 200 pixels. Setting overflow to hidden ensures that any content with dimensions larger than the container will be hidden from view.

>The second CSS rule ensures that images scale with the width of the container. The height property is set to auto, meaning an image’s height will automatically scale proportionally with the width. Finally, the last line will display images as block level elements (rather than inline-block, their default state). This will prevent images from attempting to align with other content on the page (like text), which can add unintended margin to the images.

#### Background images

```css
body {
  background-image: url('#');
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}
```






































