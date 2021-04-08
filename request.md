# Content

1. [introduction](#Introduction)
2. [HTTP-Requests](#HTTP-Requests)
3. [XHR GET Requests](#XHR-GET-Requests)


## Introduction

`HTTP` stands for <ins>Hypertext Transfer Protocol</ins> and is used to structure requests and responses over the internet. HTTP requires data to be transferred from one point to another over the network.

HTTP is the command language that the devices on both sides of the connection must follow in order to communicate.

The transfer of resources happens using `TCP` (<ins>Transmission Control Protocol</ins>).

`URL` - Uniform Resource Locator.

The GET request contains the following text:

```
GET / HTTP/1.1
Host: www.codecademy.com
```
If the server is able to locate the path requested, the server might respond with the header:
```
HTTP/1.1 200 OK
Content-Type: text/html
```
[HTTP status codes](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)

If the server is not able to locate the path requested by the client, it will respond with the header:
```
HTTP/1.1 404 NOT FOUND
```
## HTTP-Requests

JavaScript uses an event loop to handle asynchronous function calls.

When a program is run, function calls are made and added to a stack. The functions that make requests that need to wait for servers to respond then get sent to a separate queue. Once the stack has cleared, then the functions in the queue are executed.

## XHR GET Requests

**how to make an XHR GET request**
![image](https://user-images.githubusercontent.com/55635400/114035013-65bfaf00-9887-11eb-9500-49af17ea2b5f.png)

Asynchronous JavaScript and XML (AJAX), enables requests to be made after the initial page load. Initially, AJAX was used only for XML formatted data, now it can be used to make requests that have many different formats.

Similarly, the XMLHttpRequest (XHR) API, named for XML, can be used to make many kinds of requests and supports other forms of data.

Boilerplate code for an AJAX GET request using an XMLHttpRequest object.

```javascript
const xhr = new XMLHttpRequest()
const url = 'https://api-to-call.com/endpoint';
xhr.responseType = 'json';
xhr.onreadystatechange = () => {
  if(xhr.readyState === XMLHttpRequest.DONE) {
    return xhr.response;
  }
}
xhr.open('GET', url)
xhr.send()
```
