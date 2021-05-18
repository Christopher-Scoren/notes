# Content

1. [Web servers](#Web-servers)
  1. [Database](#Database)
  2. [API](#API)
  3. [Authorization and Authentication](#Authorization-and-Authentication)


## Web server
A web server is a process running on a computer that listens for incoming requests for information over the internet and sends back responses.

The specific format of a request (and the resulting response) is called the `protocol`. You might be familiar with the protocol used to access websites: HTTP. When a visitor navigates to a website on their browser, similarly to how one places an order for takeout, they make an HTTP request for the resources that make up that site.

For the simplest websites, a client makes a single request. The web server receives that request and sends the client a response containing everything needed to view the website. This is called a `static website`.

When a user navigates to google.com, their request specifies the URL but not the filename for today’s Google Doodle. The web application’s back-end will need to hold the logic for deciding which assets to send. Moreover, modern web applications often cater to the specific user rather than sending the same files to every visitor of a webpage. This is known as `dynamic content`.

The collection of programming logic required to deliver dynamic content to a client, manage security, process payments, and myriad other tasks is sometimes known as the “`application`” or `application server`. The application server can be responsible for anything from sending an email confirmation after a purchase to running the complicated algorithms a search engine uses to give us meaningful results.

### Database

The back-ends of modern web applications include some sort of `database`, often more than one. `Databases` are collections of information. There are many different databases, but we can divide them into two types: `relational databases` and `non-relational databases` (also known as NoSQL databases). Whereas relational databases store information in tables with columns and rows, non-relational databases might use other systems such as key-value pairs or a document storage model. SQL, Structured Query Language, is a programming language for accessing and changing data stored in relational databases. Popular relational databases include MySQL and PostgreSQL while popular NoSQL databases include MongoDB and Redis.

### API

In order to have consistent ways of interacting with data, a back-end will often include a web API. API stands for Application Program Interface and can mean a lot of different things, but a web API is a collection of predefined ways of, or rules for, interacting with a web application’s data, often through an HTTP request-response cycle. Unlike the HTTP requests a client makes when a user navigates to a website’s URL, this type of request indicates how it would like to interact with a web application’s data (create new data, read existing data, update existing data, or delete existing data), and it receives some data back as a response.

### Authorization and Authentication



