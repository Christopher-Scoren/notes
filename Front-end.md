# Content
1. [Introduction](#Introduction)
2. [HTML](#HTML)  
  1.[Table](#table)  
  2.[Semantic HTML](#semantic-html)  
3. xnjnj


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

Tags:

`<h1></h1>`                  - headding (1-6)  
`<p></p>`                    - paragraph  
`<a href="something"></a>`   - link  
`<button></button>`          - button  

[html5-tag-cheat-sheet-2019.pdf](https://github.com/Christopher-SinCoren/notes/files/6513356/html5-tag-cheat-sheet-2019.pdf)


### Table
[Content](#content)

![image](https://user-images.githubusercontent.com/55635400/118930267-356f3400-b94e-11eb-90d6-ea7be974f4fa.png)

We can use the scope attribute on <th> elements to indicate whether a <th> element is being used as a "row" heading or a "col" heading.

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
  
```html
<!DOCTYPE html>
<html>
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
  
  
