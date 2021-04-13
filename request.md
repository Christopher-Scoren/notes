# Content

1. [introduction](#Introduction)
2. [HTTP-Requests](#HTTP-Requests)
3. [XHR GET Requests](#XHR-GET-Requests)
4. [XHR POST Requests](#XHR-POST-Requests)


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

A **query string** contains additional information to be sent with a request. A query string is separated from the URL using a `?` character. After ?, you can then create a parameter which is a key value pair joined by a =.  
`'https://api.datamuse.com/words?key=value'`

If you want to add an additional parameter you will have to use the & character to separate your parameters.  
`'https://api.datamuse.com/words?key=value&anotherKey=anotherValue'`


## XHR POST Requests

The major difference between a GET request and POST request is that a POST request requires additional information to be sent through the request. This additional information is sent in the body of the post request.

![image](https://user-images.githubusercontent.com/55635400/114509234-f4dd1600-9c3d-11eb-9b18-14382254b46e.png)

> JSON.stringify() will convert a value to a JSON string. By converting the value to a string, we can then send the data to a server.
 
```js
const xhr = new XMLHttpRequest();
const url = 'https://api-to-call.com/endpoint';
const data = JSON.stringify({id: '200'});
xhr.responseType = 'json';
xhr.onreadystatechange = () => {
  if(xhr.readyState === XMLHttpRequest.DONE){
    return xhr.response;
  }
}
xhr.open('POST', url);
xhr.send(data);
```
## fetch() GET Requests

The fetch() function:

![image](https://user-images.githubusercontent.com/55635400/114529697-e64d2980-9c52-11eb-8006-a6794b19a88f.png)

Creates a request object that contains relevant information that an API needs.
Sends that request object to the API endpoint provided.
Returns a promise that ultimately resolves to a response object, which contains the status of the promise with information the API sent back.

```js
//boilerplate for fetch function

fetch('https://api-to-call.com/endpoint').then(response => {
  if(response.ok){
    return response.json();
  }
  throw new Error('Request failed!');
}, networkError => {
  console.log(networkError.message);
}).then(jsonResponse => {
  return jsonResponse;
});
```
## fetch() POST

![image](https://user-images.githubusercontent.com/55635400/114533249-5f01b500-9c56-11eb-8517-22c8c14d8a45.png)

```js
//boilerplate

fetch('https://api-to-call.com/endpoint', {
  method: 'POST',
  body: JSON.stringify({id: '200'})
}).then(response => {
  if(response.ok){
    return response.json();
  }
  throw new Error('Request failed!');
}, networkError => {
  console.log(networkError.message);
}).then(jsonResponse => {
  return jsonResponse;
})
```
## async GET Requests

![image](https://user-images.githubusercontent.com/55635400/114544409-3fbd5480-9c63-11eb-9807-96846a3f40b8.png)

```js
//boilerplate

const getData = async () => {
  try {
    const response = await fetch('https://api-to-call.com/endpoint');
    if (response.ok){
      const jsonResponse = await response.json();
      return jsonResponse;
    }
    throw new Error('Request failed!');
  } catch (error){
    console.log(error);
  }
}
```

## async POST Requests

![image](https://user-images.githubusercontent.com/55635400/114545934-3af9a000-9c65-11eb-9dcb-de0b735998c9.png)

```js
//boilerplate

const getData = async () => {
  try {
    const response = await fetch('https://api-to-call.com/endpoint', {
      method: 'POST',
      body: JSON.stringify({id: 200})
    });
    if (response.ok){
      const jsonResponse = await response.json();
      return jsonResponse;
    }
    throw new Error('Request failed!');
  } catch(error){
    console.log(error);
  }
}
```
## reviewing Requests

1. GET and POST requests can be created a variety of ways.
2. Use AJAX to asynchronously request data from APIs. fetch() and async/await are new functionalities developed in ES6 (promises) and ES8 respectively.
3. Promises are a new type of JavaScript object that represent data that will eventually be returned from a request.
4. fetch() is a web API that can be used to create requests. fetch() will return promises.
5. We can chain .then() methods to handle promises returned by fetch().
6. The .json() method converts a returned promise to a JSON object.
7. async is a keyword that is used to create functions that will return promises.
8. await is a keyword that is used to tell a program to continue moving through the message queue while a promise resolves.
9. await can only be used within functions declared with async.
