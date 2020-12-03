# ExpressJS DevRef <!-- omit in toc -->

- [Express Basics](#express-basics)
  - [Setting Up Express](#setting-up-express)
  - [Connecting Additional Packages](#connecting-additional-packages)
  - [Creating Routes](#creating-routes)
    - [GET Routes - To Request Data From Server](#get-routes---to-request-data-from-server)
    - [POST Routes - To Send Data To Server](#post-routes---to-send-data-to-server)
- [Popular Packages To Use With Express](#popular-packages-to-use-with-express)
  - [`body-parser` Package](#body-parser-package)
  - [CORS Package](#cors-package)
    - [Usage of CORS with ExpressJS](#usage-of-cors-with-expressjs)
      - [Simple Usage (Enable All CORS Requests)](#simple-usage-enable-all-cors-requests)
      - [Enable CORS for a Single Route](#enable-cors-for-a-single-route)

## Express Basics

### Setting Up Express

To install express, we use the `npm install express` command in the terminal. Using Express we set up an instance of our web app like this:

```javascript
// Express to run server and routes
const express = require("express");

// Start up an instance of app
const app = express();
```

### Connecting Additional Packages

Once we have created an instance of our app using Express, we can connect the other packages we have installed on the command line to our app in our code with the `.use()` method.

```javascript
app.use(packageName());
```

### Creating Routes

#### GET Routes - To Request Data From Server

```javascript
app.get("/all", sendData);

function sendData(request, response) {
  response.send(projectData);
}
```

You could also just pass a function in as the second parameter to `.get()` like this:

```javascript
app.get("/all", function(request, response) {
  response.send(projectData);
});
```

Or even with an arrow function like this:

```javascript
app.get("/all", (request, response) => {
  response.send(projectData);
});
```

#### POST Routes - To Send Data To Server

An HTTP POST request sends data to the defined endpoint, where it is stored and can be accessed through a GET request.

Let us say that the end point is a constant called `data`:

```javascript
const data = [];
```

We can create a `post()` with a url path and a callback function:

```javascript
app.post("/addMovie", addMovie);
```

The data to be received is stored in `request.body`.

We can access and work with the received data in the callback function.

```javascript
function addMovie(req, res) {
  console.log(req.body);
  data.push(req.body);
}
```

## Popular Packages To Use With Express

### `body-parser` Package

Express version 4 and above require extra middle-ware layer to handle a POST request. This middle-ware is called as `bodyParser`. This used to be an internal part of Express framework, but now you have to install it separately.

```javascript
/* Connecting body-parser */
const bodyParser = require("body-parser");

/* Middleware*/
//Here we are configuring express to use body-parser as middle-ware.
app.use(bodyParser.urlencoded({ extended: false }));
app.use(bodyParser.json());
```

### CORS Package

The below description is from [Wikipedia CORS Article](https://en.wikipedia.org/wiki/Cross-origin_resource_sharing):

_Cross-origin resource sharing (CORS) is a mechanism that allows restricted resources on a web page to be requested from another domain outside the domain from which the first resource was served._

_A web page may freely embed cross-origin images, stylesheets, scripts, iframes, and videos. Certain "cross-domain" requests, notably Ajax requests, are forbidden by default by the same-origin security policy. CORS defines a way in which a browser and server can interact to determine whether it is safe to allow the cross-origin request. It allows for more freedom and functionality than purely same-origin requests, but is more secure than simply allowing all cross-origin requests._

#### Usage of CORS with ExpressJS

Below code snippets are from [ExpressJS - Middleware CORS Refernce Page](https://expressjs.com/en/resources/middleware/cors.html).

##### Simple Usage (Enable All CORS Requests)

```javascript
var express = require("express");
var cors = require("cors");
var app = express();

app.use(cors());

app.get("/products/:id", function(req, res, next) {
  res.json({ msg: "This is CORS-enabled for all origins!" });
});

app.listen(80, function() {
  console.log("CORS-enabled web server listening on port 80");
});
```

##### Enable CORS for a Single Route

```javascript
app.get("/products/:id", cors(), function(req, res, next) {
  res.json({ msg: "This is CORS-enabled for a Single Route" });
});

app.listen(80, function() {
  console.log("CORS-enabled web server listening on port 80");
});
```
