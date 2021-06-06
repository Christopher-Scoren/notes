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
  8.[Media queries](#media-queries)  
  9.[Undestanding responsiveness](#undestanding-responsiveness)  
  10.[Grids and spacing](#grids-and-spacing)  
  


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

### Media queries

CSS uses `media queries` to adapt a website’s content to different screen sizes. With media queries, CSS can detect the size of the current screen and apply different CSS styles depending on the width of the screen.
```css
@media only screen and (max-width: 480px) {
  body {
    font-size: 12px;
  }
}
```

* `@media` — This keyword begins a media query rule and instructs the CSS compiler on how to parse the rest of the rule.
* `only screen` — Indicates what types of devices should use this rule. In early attempts to target different devices, CSS incorporated different media types (screen, print, handheld). The rationale was that by knowing the media type, the proper CSS rules could be applied. However, “handheld” and “screen” devices began to occupy a much wider range of sizes and having only one CSS rule per media device was not sufficient. screen is the media type always used for displaying content, no matter the type of device.  
* The `only` keyword is added to indicate that this rule only applies to one media type (screen).
`and (max-width : 480px)` — This part of the rule is called a media feature, and instructs the CSS compiler to apply the CSS styles to devices with a width of 480 pixels or smaller. Media features are the conditions that must be met in order to render the CSS within a media query.
* CSS rules are nested inside of the media query’s curly braces. The rules will be applied when the media query is met. In the example above, the text in the body element is set to a font-size of 12px when the user’s screen is less than 480px.

#### Rance
```css
@media only screen and (min-width: 320px) and (max-width: 480px) {
    /* ruleset for 320px - 480px */
}
```
OR
```css
@media only screen and (min-width: 320px) { 
    /* ruleset for >= 320px */
}
 
 
@media only screen and (min-width: 480px) { 
    /* ruleset for >= 480px */
}
```

#### Dots per inch (DPI)

Another media feature we can target is screen resolution. Many times we will want to supply higher quality media (images, video, etc.) only to users with screens that can support high resolution media. Targeting screen resolution also helps users avoid downloading high resolution (large file size) images that their screen may not be able to properly display.
```css
@media only screen and (min-resolution: 300dpi) {
    /* CSS for high resolution screens */
}
```

#### AND operator
```css
@media only screen and (max-width: 480px) and (min-resolution: 300dpi) {
    /* CSS ruleset */
}
```

#### Comma Separated List

If only one of multiple media features in a media query must be met, media features can be separated in a comma separated list.
```css
@media only screen and (min-width: 480px), (orientation: landscape) {
    /* CSS ruleset */
}
```
The points at which media queries are set are called breakpoints. Breakpoints are the screen sizes at which your web page does not appear properly. For example, if we want to target tablets that are in landscape orientation, we can create the following breakpoint:
```css
@media only screen and (min-width: 768px) and (max-width: 1024px) and (orientation: landscape) {
    /* CSS ruleset */
}
```
![image](https://user-images.githubusercontent.com/55635400/119940622-23b60e00-bf98-11eb-9c11-e60b015f273b.png)

### Undestanding responsiveness

1. Define Viewport

Before you do anything else, you have to define the width of the viewport in your HTML. This will ensure that your site has no horizontal scroll - the full site will be visible, and users will not have to zoom on mobile to see the content.
```html
<meta name="viewport" content="width=device-width, initial-scale=1" />
```
2. Include a Browser Reset
just use this [reset css code](https://meyerweb.com/eric/tools/css/reset/)
or [this one](http://necolas.github.io/normalize.css/) / [css code](https://cdnjs.cloudflare.com/ajax/libs/normalize/3.0.3/normalize.min.css)

3. Reset Border Box
```css
Reset Border Box
```

4.Include jQuery (optional)
```html
<script src="js/jquery.min.js"></script>
```

5. Breakpoints
`mobile first` - The concept is that you build your content to look great for mobile, and scale up from there. This is a good philosophy to work with.

### Grids and spacing

`Grids` are made up of intersecting horizontal and vertical lines.

Types of grids:
* block grid
* column grid


Grid's structure:

![image](https://user-images.githubusercontent.com/55635400/120599341-0c6f9880-c450-11eb-811b-6f305ec7b17c.png)

`Columns` are defined as the vertical sections that span the width of a page. In web design, it’s common to see layouts consisting of 12 or 16 columns, while other may only feature three columns. Defining the number of columns depends on what’s appropriate for your design, device, and or screen viewing size.

a `gutter` is the negative space between each column. Gutters help in ensuring the columns don’t run together, which would negate the purpose of using a column-based grid.

`Margins` appear on the left and right sides of the column-based grid. These ensure the content of your designs doesn’t match up to the edges of the browser window.

`Columns` are the vertical containers that span the width of the page. They can be dependent on each other, meaning they are used to organize related content such as a continuation of a paragraph. They can also be independent of each other, meaning they are used for organizing the layout of unrelated content such as a sidebar. 

>Within a grid, content can span multiple columns. What this means is that a website does not need to maintain the same column layout throughout. For example, a section of a website with a 12 column grid can have content that spans 4 columns, three times.

  * No content can spill into the gutter unless it is using the next column.

`Rows` are the horizontal lines on a grid. Think of rows as invisible boxes that groups content together by height. 

`Whitespace`, or `negative space`, refers to the emptiness between elements. Whether that’s in the gutter of the columns, or additional padding around a block of text.

`passive whitespace` or `micro whitespace` - 

>Used to improve the aesthetics of the layout without guiding the user through a specific reading, flow, or content order, passive whitespace is sometimes referred to as the unconsidered space. The most frequent use of passive whitespace comes within text elements.  
>>Different font families have varying amounts of passive whitespace and you can control aspects of them within your design by altering CSS properties such as such as line-height or margin when setting type.

`active whitespace` is intentional. Also called `macro whitespace`, active whitespace refers to enhancing the overall page structure through space to emphasize content or guide users from one point to the next.

**Whereas Flexbox is mostly useful for positioning items in a one-dimensional layout, CSS grid is most useful for two-dimensional layouts, providing many tools for aligning and moving elements across both rows and columns.**

#### Creating a grid

* To set up a grid, you need to have both a grid container and grid items. 

The grid container will be a parent element that contains grid items as children and applies overarching styling and positioning to them.

To turn an HTML element into a grid container, you must set the element’s display property to one of two values:

* `grid` — for a block-level grid.
* `inline-grid` — for an inline grid.

**By default, grids contain only one column.**

define the columns of our grid
```css
.grid {
  display: grid;
  width: 500px;
  grid-template-columns: 100px 200px;
}
```
This property creates two changes. First, it defines the number of columns in the grid; in this case, there are two. Second, it sets the width of each column. The first column will be 100 pixels wide and the second column will be 200 pixels wide.

We can also define the size of our columns as a percentage of the entire grid’s width.
```css
.grid {
  display: grid;
  width: 1000px;
  grid-template-columns: 20% 50%;
}

/* mix */
.grid {
  display: grid;
  width: 100px;
  grid-template-columns: 20px 40% 60px;
}

/* overflow */
.grid {
  display: grid;
  width: 100px;
  grid-template-columns: 20px 40% 60px; /* 120px in total */
}
```

* `grid-template-rows` - To specify the number and size of the rows

```css
grid-template-rows: 10% 20% 600px; /* three rows */
```
**When using percentages in these two properties, remember that rows are defined as a percentage of the grid’s height, and columns are defined as a percentage of its width.**

* `grid-template` - shorthand for both above
```css
.grid{
    grid-template: 200px 300px / 20% 10% 70%; /* rows / columns */
}
```

Grid introduced a new relative sizing unit — `fr`, like `fraction`.

>By using the fr unit, we can define the size of columns and rows as a fraction of the grid’s length and width. This unit was specifically created for use in CSS Grid. Using fr makes it easier to prevent grid items from overflowing the boundaries of the grid. 

```css
./grid {
    grid-template: 2fr 1fr 1fr / 1fr 3fr 1fr;
}
```
>In this example, the grid will have three rows and three columns. The rows are splitting up the available 400 pixels of height into four parts. The first row gets two of those parts, the second row gets one, and the third row gets one. Therefore the first row is 200 pixels tall, and the second and third rows are 100 pixels tall.

It is possible to use fr with other units as well. When this happens, each fr represents a fraction of the available space.
```css
.grid{
  display: grid;
  width: 100px;
  grid-template-columns: 1fr 60px 1fr;
}
```

#### Function

The properties that define the number of rows and columns in a grid can take a `function` as a value. `repeat()` is one of these functions. The repeat() function was created specifically for CSS Grid.
```css
.grid {
  display: grid;
  width: 300px;
  grid-template-columns: repeat(3, 100px);
}

/* same as: */
  grid-template-columns: 100px 100px 100px;
```
Repeat is particularly useful with fr. For example, `repeat(5, 1fr)` would split your table into five equal rows or columns.

Finally, the second parameter of repeat() can have multiple values.
```css
  grid-template-columns: repeat(2, 20px 50px)
```
This code will create four columns where the first and third columns will be 20 pixels wide and the second and fourth will be 50 pixels wide.

#### minmax function

```css
.grid {
  display: grid;
  grid-template-columns: 100px minmax(100px, 500px) 100px;
}
```
>In this example, the first and third columns will always be 100 pixels wide, no matter the size of the grid. The second column, however, will vary in size as the overall grid resizes. The second column will always be between 100 and 500 pixels wide.

#### Grid gap
```css
.grid {
  display: grid;
  width: 320px;
  grid-template-columns: repeat(3, 1fr);
  grid-column-gap: 10px;
}

/* shorthand */
.grid {
  display: grid;
  width: 320px;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 20px 10px; /* row + column */
}
```
* It is important to note that grid gap properties does not add space at the beginning or end of the grid. In the example code, our grid will have three columns with two ten-pixel gaps between them.

* Unlike other CSS grid properties, this shorthand does not take a / between values! If only one value is given, it will set the column gap and the row gap to that value.

#### grid items

make single grid items take up multiple rows.
```css
.item {
  grid-row-start: 1;
  grid-row-end: 4;
}

/* shorthand for previous */
.item {
  grid-row: 1 / 4;
}
```
>In this example, the HTML element of class item will take up two rows in the grid, rows 1 and 2. The values that grid-row-start and grid-row-end accept are grid lines.  
>>Row grid lines and column grid lines start at 1 and end at a value that is 1 greater than the number of rows or columns the grid has. For example, if a grid has 5 rows, the grid row lines range from 1 to 6. If a grid has 8 rows, the grid row lines range from 1 to 9.

* It is possible for the value of grid-row-start to be greater than that of grid-row-end. Both properties can also each have negative values. 

Make single grid item take up multiple columns
```css
.item {
  grid-column: 4 / span 2; /* count 2 rows from 4th */
}

/* same as */
.item {
  grid-column: 4 / 6;
}
.item {
  grid-column-start: 4;
  grid-column-end: span 2;
}
.item {
  grid-column-start: span 2;
  grid-column-end: 6;
}
```

* refactoring `grid-row` and `grid-column`:
```css
.item {
  grid-area: 2 / 3 / 4 / span 5; /* grid-row-start -> grid-column-start -> grid-row-end -> grid-column-end */
}
```
>In the above example, the item will occupy rows two and three and columns three through eight.


#### Grid template areas

The `grid-template-areas` property allows you to name sections of your web page to use as values in the grid-row-start, grid-row-end, grid-column-start,grid-column-end, and grid-area properties. This property is declared on grid containers.
```html
<div class="container">
  <header>Welcome!</header>
  <nav>Links!</nav>
  <section class="info">Info!</section>
  <section class="services">Services!</section>
  <footer>Contact us!</footer>
</div>
```
```css
.container {
  display: grid;
  max-width: 900px;
  position: relative;
  margin: auto;
  grid-template-areas: "head head"
                       "nav nav" 
                       "info services"
                       "footer footer";
  grid-template-rows: 300px 120px 800px 120px;
  grid-template-columns: 1fr 3fr; 
}
 
header {
  grid-area: head;
} 
 
nav {
  grid-area: nav;
} 
 
.info {
  grid-area: info;
} 
 
.services {
  grid-area: services;
}
 
footer {
  grid-area: footer;
} 
```
* In the example above, the HTML creates a web page with five distinct parts.  
* In the .container ruleset, the grid-template-areas declaration creates a 2-column, 4-row layout.  
* The grid-template-rows declaration specifies the height of each of the four rows from top to bottom: 300 pixels, 120 pixels, 800 pixels, and 120 pixels.  
* The grid-template-columns declaration uses the fr value to cause the left column to use one fourth of the available space on the page and the right column to use three-fourths of the available space on the page.  
* In each ruleset below .container, we use the grid-area property to tell that section to cover the portion of the page specified. The header element spans the first row and both columns. The nav element spans the second row and both columns. The element with class .info spans the third row and left column. The element with class .services spans the third row and right column. The footer element spans the bottom row and both columns.  


#### overlap
```html

```
```css
.container {
  display: grid;
  grid-template: repeat(8, 200px) / repeat(6, 100px);
}
 
.info {
  grid-area: 1 / 1 / 9 / 4;
}
 
.services {
  grid-area: 1 / 4 / 9 / 7;
}
 
img {
  grid-area: 2 / 3 / 5 / 5;
  z-index: 5;
}
```
>The z-index property tells the browser to render the image element on top of the services and info sections so that it is visible.

The z-index property tells the browser to render the image element on top of the services and info sections so that it is visible.

![image](https://user-images.githubusercontent.com/55635400/120916638-750a7f80-c6b3-11eb-97ec-a26be63a88a2.png)

#### Justify items

There are two axes in a grid layout — the column (or block) axis and the row (or inline) axis.  
The column axis stretches from top to bottom across the web page. The row axis stretches from left to right across the web page.

```html
<main>
  <div class="card">Card 1</div>
  <div class="card">Card 2</div>
  <div class="card">Card 3</div>
</main>
```
```css
main {
  display: grid;
  grid-template-columns: repeat(3, 400px);
  justify-items: center; /* start / end / center / stretch */
}
```

#### justify-content

We can use justify-content to position the entire grid along the row axis. This property is declared on grid containers.
```html
<main>
  <div class="left">Left</div>
  <div class="right">Right</div>
</main>
```
```css
main {
  display: grid;
  width: 1000px;
  grid-template-columns: 300px 300px;
  grid-template-areas: "left right"; 
  justify-content: center; /* start / end / center / stretch / space-around / space-between / space-evenly */
}
```

#### align-items
```html
<main>
  <div class="card">Card 1</div>
  <div class="card">Card 2</div>
  <div class="card">Card 3</div>
</main>
```
```css
main {
  display: grid;
  grid-template-rows: repeat(3, 400px);
  align-items: center; /* start / end / center / stretch */
}
```
#### align-content
```html
<main>
  <div class="top">Top</div>
  <div class="bottom">Bottom</div>
</main>
```
```css
main {
  display: grid;
  height: 600px;
  grid-template-rows: 200px 200px;
  grid-template-areas: "top"
                       "bottom"; 
  align-content: center;
}
```
#### justify-self
The justify-items and align-items properties specify how all grid items contained within a single container will position themselves along the row and column axes, respectively.

justify-self specifies how an individual element should position itself with respect to the row axis. This property will override justify-items for any item on which it is declared.

align-self specifies how an individual element should position itself with respect to the column axis. This property will override align-items for any item on which it is declared.

align-self and justify-self accept the same values as align-items and justify-items. 

#### Implicit vs. Explicit Grid

The `implicit grid` is an algorithm built into the specification for CSS Grid that determines default behavior for the placement of elements when there are more than fit into the grid specified by the CSS.

The default behavior of the implicit grid is as follows: items fill up rows first, adding new rows as necessary. New grid rows will only be tall enough to contain the content within them. 

#### Grid Auto Rows and Grid Auto Columns

CSS Grid provides two properties to specify the size of grid tracks added implicitly: `grid-auto-rows` and `grid-auto-columns`. These properties are declared on grid containers.

grid-auto-rows specifies the height of implicitly added grid rows. grid-auto-columns specifies the width of implicitly added grid columns.

grid-auto-rows and grid-auto-columns accept the same values as their explicit counterparts, grid-template-rows and grid-template-columns: px, ft, %, repeat();

```html
<body>
  <div>Part 1</div>   
  <div>Part 2</div>
  <div>Part 3</div>
  <div>Part 4</div>
  <div>Part 5</div>
</body>
```
```css
body {
  display: grid;
  grid: repeat(2, 100px) / repeat(2, 150px); 
  grid-auto-rows: 50px;
}
```
>In the example above, there are 5 <.div>s. However, in the body ruleset, we only specify a 2-row, 2-column grid — four grid cells. The fifth <.div> will be added to an implicit row that will be 50 pixels tall If we did not specify grid-auto-rows, the rows would be auto-adjusted to the height of the content of the grid items.

#### Grid Auto Flow

grid-auto-flow specifies whether new elements should be added to rows or columns, and is declared on grid containers.

grid-auto-flow accepts these values:

* row — specifies the new elements should fill rows from left to right and create new rows when there are too many elements (default)  
* column — specifies the new elements should fill columns from top to bottom and create new columns when there are too many elements  
* dense — this keyword invokes an algorithm that attempts to fill holes earlier in the grid layout if smaller elements are added

  * You can pair row or column with dense, like this: grid-auto-flow: row dense;.


















