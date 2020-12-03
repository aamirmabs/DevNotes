# JavaScript DevRef <!-- omit in toc -->

- [Destructuring](#destructuring)
  - [Destructuring Values From Arrays](#destructuring-values-from-arrays)
    - [Ignoring Values While Destructuring Arrays](#ignoring-values-while-destructuring-arrays)
  - [Destructuring Values From Objects](#destructuring-values-from-objects)
    - [Ignoring Values While Destructuring Objects](#ignoring-values-while-destructuring-objects)
- [Object Literals](#object-literals)
- [JavaScript and the DOM](#javascript-and-the-dom)
  - [Selecting HTML Elements](#selecting-html-elements)
    - [Selecting Elements By Tag](#selecting-elements-by-tag)
    - [Selecting Elements By Class](#selecting-elements-by-class)
    - [Selecting Elements By ID](#selecting-elements-by-id)
  - [Modifying HTML Elements](#modifying-html-elements)
    - [`.innerHTML` Property](#innerhtml-property)
    - [`.innerHTML` and `.outerHTML` Property](#innerhtml-and-outerhtml-property)
    - [`.textContent` Property](#textcontent-property)
    - [`.innerText` Property](#innertext-property)
  - [Creating HTML Elements](#creating-html-elements)
    - [`document.createElement()`](#documentcreateelement)
    - [`document.appendElement()`](#documentappendelement)
    - [`.insertAdjacentHTML()`](#insertadjacenthtml)
  - [Removing HTML Elements](#removing-html-elements)
    - [`.removeChild()`](#removechild)
    - [`.remove()`](#remove)
  - [Modifying CSS Properties](#modifying-css-properties)
    - [Modifying an Element's Style Attribute](#modifying-an-elements-style-attribute)
    - [Adding Multiple Styles At Once](#adding-multiple-styles-at-once)
    - [Setting An Element's Attributes](#setting-an-elements-attributes)
    - [Accessing an Element's Classes](#accessing-an-elements-classes)
    - [The .classList Property](#the-classlist-property)
  - [DOM Events](#dom-events)
    - [Event Listener](#event-listener)
    - [Event Phases](#event-phases)
- [Asynchronous JavaScript](#asynchronous-javascript)
  - [JavaScript Promises](#javascript-promises)
    - [Running Promises in Parallel](#running-promises-in-parallel)

## Destructuring

Destructuring borrows inspiration from languages like Perl and Python by allowing you to specify the elements you want to extract from an array or object on the left side of an assignment.

### Destructuring Values From Arrays

```javascript
const point = [10, 25, -34];

const [x, y, z] = point;

console.log(x, y, z);
```

The brackets `[ ]` represent the array being destructured and x, y, and z represent the variables where you want to store the values from the array.

#### Ignoring Values While Destructuring Arrays

The statement `const [x, , z] = point;` will ignore the `y` coordinate and discards it.

### Destructuring Values From Objects

```javascript
const gemstone = {
  type: "quartz",
  color: "rose",
  carat: 21.29
};

const { type, color, carat } = gemstone;

console.log(type, color, carat);
```

#### Ignoring Values While Destructuring Objects

Unlike arrays, you can destructure and obtain a a single value from an object. For example, `const { type } = gemstone;` will extract the value of `gemstone[type]` into the variable `type`.

Similar to destructuring arrays, you can ignore specific values while destructuring an object. For example, `gemstone[color]` will be ignored in the snippet below:

```javascript
const gemstone = {
  type: "quartz",
  color: "rose",
  carat: 21.29
};

const { type, , carat } = gemstone;
```

## Object Literals

Ideally if we had to assign variables to an object, we would write something like this:

```javascript
let type = "quartz";
let color = "rose";
let carat = 21.29;

const gemstone = {
  type: type,
  color: color,
  carat: carat,

  calculateWorth: function() {
    // will calculate worth of gemstone based on type, color, and carat
  }
};

console.log(gemstone);
// o/p : Object {type: "quartz", color: "rose", carat: 21.29}
```

As the names of the variables and the object properties are the same, we can rewrite the code as below:

```javascript
let type = "quartz";
let color = "rose";
let carat = 21.29;

const gemstone = {
  type,
  color,
  carat,

  calculateWorth() {
    // will calculate worth of gemstone based on type, color, and carat
  }
};

console.log(gemstone);
// o/p : Object {type: "quartz", color: "rose", carat: 21.29}
```

## JavaScript and the DOM

### Selecting HTML Elements

#### Selecting Elements By Tag

#### Selecting Elements By Class

#### Selecting Elements By ID

### Modifying HTML Elements

#### `.innerHTML` Property

Represents the markup of the element's content. We can use this property to:

- get an element's (and all of its descendants!) HTML content
- set an element's HTML content

```html
<h1 id="pick-me">Greetings To <span>All</span>!</h1>
```

```javascript
const innerResults = document.querySelector("#pick-me").innerHTML;
console.log(innerResults); // logs the string: "Greetings To <span>All</span>!"

const outerResults = document.querySelector("#pick-me").outerHTML;
console.log(outerResults); // logs the string: "<h1 id="pick-me">Greetings To <span>All</span>!</h1>"
```

#### `.innerHTML` and `.outerHTML` Property

The `.innerHTML` property sets or returns the HTML content inside the selected element (i.e. between the tags).

There's also the rarely used `.outerHTML` property. `.outerHTML` represents the HTML element itself, as well as its children.

```html
<h1 id="pick-me">Greetings To <span>All</span>!</h1>
```

```javascript
const innerResults = document.querySelector("#pick-me").innerHTML;
console.log(innerResults); // logs the string: "Greetings To <span>All</span>!"

const outerResults = document.querySelector("#pick-me").outerHTML;
console.log(outerResults); // logs the string: "<h1 id="pick-me">Greetings To <span>All</span>!</h1>"
```

#### `.textContent` Property

If we just want the text content, use the `.textContent` property.

The `.textContent` property will:

- set the text content of an element and all its descendants
- return the text content of an element and all its descendants

```javascript
chosenElement.textContent =
  "I will be the updated text for the nanodegreeCard element!";
```

NOTE: Passing text that contains HTML characters to `.textContent` will not display the content as HTML. Instead, it will still display everything as text - even the HTML characters.

So if we passed the content `This is <strong>Bold</strong> Text.`, it will not display the converted HTML version with emphasized `Bold`. It will display the plain-text `<strong>Bold</strong>`.

#### `.innerText` Property

Both `.innerText` and `.textContent` can be used to set the HTML content of an element, but there are a few important differences which we should keep in our mind.

`.textContent` sets/gets the text content of an element. When getting the content, it will get **only the _visible_** content.

So, if there are any elements that are hidden by CSS or based on some conditions by JavaScript, then they are not obtained.

Between `.textContent` and `.innerText`, you probably want to use `.textContent` since that will return all of the text no matter what.

### Creating HTML Elements

#### `document.createElement()`

```javascript
// creates and returns a <span> element
document.createElement("span");

// creates and returns an <h3> element
document.createElement("h3");
```

#### `document.appendElement()`

Creating an element...just creates it. It doesn't add it to the DOM. Since the element isn't added to the DOM, it doesn't appear in the page.

We use the `.appendChild()` method to add an element to the page!

```javascript
// create a brand new <span> element
const newSpan = document.createElement("span");

// select the first (main) heading of the page
const mainHeading = document.querySelector("h1");

// add the the <span> element as the last child element of the main heading
mainHeading.appendChild(newSpan);
```

The `.appendChild()` method is called on one element, and is passed the element to append. The element that is about to be appended is added as the last child. So, in the example above, the `<span>` element will appear in the DOM as a child of the `<h1>`...but it will appear at the end, after all text and any other elements that might be in the `<h1>`.

#### `.insertAdjacentHTML()`

The `.insertAdjacentHTML()` method has to be called with two arguments:

- the location of the HTML
- the HTML text that is going to be inserted

The first argument to this method will let us insert the new HTML in one of four different locations

- `beforebegin` – inserts the HTML text as a previous sibling
- `afterbegin` – inserts the HTML text as the first child
- `beforeend` – inserts the HTML text as the last child
- `afterend` – inserts the HTML text as a following sibling

```html
<!-- beforebegin -->
<p>
  <!-- afterbegin -->
  Existing text/HTML content
  <!-- beforeend -->
</p>
<!-- afterend -->
```

```javascript
const mainHeading = document.querySelector("#main-heading");
const htmlTextToAdd = "<h2>Skydiving is fun!</h2>";

mainHeading.insertAdjacentHTML("afterend", htmlTextToAdd);
```

Note: The text added in the `.insertAdjacentHTML()` will be plain text and not HTML. You cannot pass an element.

### Removing HTML Elements

#### `.removeChild()`

`.removeChild()` method requires:

- a parent element
- the child element that will be removed

If we have access to the child element that we're about to add or remove, you can use the `parentElement` property to "move focus" to the element's parent. Then we can call `.removeChild()` (or `.appendChild()`) on that referenced parent element.

Let's look at an example:

```javascript
const mainHeading = document.querySelector("h1");

mainHeading.parentElement.removeChild(mainHeading);
```

#### `.remove()`

`.remove()` removes the chosen element.

```javascript
const mainHeading = document.querySelector("h1");

mainHeading.remove();
```

### Modifying CSS Properties

#### Modifying an Element's Style Attribute

```javascript
const mainHeading = document.querySelector("h1");

mainHeading.style.color = "red";
```

#### Adding Multiple Styles At Once

If we wanted to set an element's color, background color, and font size, we'd have to use three separate lines of code

```javascript
const mainHeading = document.querySelector("h1");

mainHeading.style.color = "blue";
mainHeading.style.backgroundColor = "orange";
mainHeading.style.fontSize = "3.5em";
```

Instead of using one statement for each of the properties, we can club all of them into a single statement.

```javascript
const mainHeading = document.querySelector("h1");

mainHeading.style.cssText =
  "color: blue; background-color: orange; font-size: 3.5em";
```

#### Setting An Element's Attributes

```javascript
const mainHeading = document.querySelector("h1");

mainHeading.setAttribute(
  "style",
  "color: blue; background-color: orange; font-size: 3.5em;"
);
```

The `setAttribute()` method is not just for styling page elements. You can use this method to set any attribute for an element. You can give an element an ID with:

```javascript
const mainHeading = document.querySelector("h1");

// add an ID to the heading's sibling element
mainHeading.nextElementSibling.setAttribute("id", "heading-sibling");

// use the newly added ID to access that element
document.querySelector("#heading-sibling").style.backgroundColor = "red";
```

#### Accessing an Element's Classes

We could use .className to access the list of classes:

```javascript
const mainHeading = document.querySelector("#main-heading");

// store the list of classes in a variable
const listOfClasses = mainHeading.className;

// logs out the string "ank-student jpk-modal"
console.log(listOfClasses);
```

The `.className` property returns a space-separated string of the classes. This isn't the most ideal format, unfortunately. We can, however, convert this space-separated string into an array using the JavaScript string method, `.split()`:

```javascript
const arrayOfClasses = listOfClasses.split(" ");

// logs out the array of strings ["ank-student", "jpk-modal"]
console.log(arrayOfClasses);
```

Now that we have an array of classes, we can do any data-intensive calculations:

- use a for loop to loop through the list of class names
- use `.push()` to add an item to the list
- use `.pop()` to remove an item from the list

`.className` is a property, so we can set its value just by assigning a string to the property:

```javascript
mainHeading.className = "im-the-new-class";
```

The above code **erases any classes** that were originally in the element's class attribute and replaces it with the single class `im-the-new-class`.

Since `.className` returns a string, it makes it hard to add or remove individual classes. We can convert the string to an array and then use different Array Methods to search for a class remove it from the list, and then update the `.className` with the remaining classes.

#### The .classList Property

`classList()` returns a DOMTokenList.

```html
<h1 id="main-heading" class="ank-student jpk-modal">
  Learn Web Development at Udacity
</h1>
```

```javascript
const mainHeading = document.querySelector("#main-heading");

// store the list of classes in a variable
const listOfClasses = mainHeading.classList;

// logs out ["ank-student", "jpk-modal"]
console.log(listOfClasses);
```

The `.classList` property has a number of properties of its own. Some of the most popularly used ones are:

- `.add()` - to add a class to the list
- `.remove()` - to remove a class from the list
- `.toggle()` - to add the class if it doesn't exists or remove it from the list if it does already exist
- `.contains()` - returns returns a boolean based on if the class exists in the list or not

### DOM Events

You can view any events that are triggered on an element with `monitorEvents(element)`. If we want to view all the events that are active on the `document` object we will pass `document` as the argument to the function.

```javascript
// start displaying all events on the document object
monitorEvents(document);

// turn off the displaying of all events on the document object.
unmonitorEvents(document);
```

#### Event Listener

```javascript
const mainHeading = document.querySelector("h1");

mainHeading.addEventListener("click", function() {
  console.log("The heading was clicked!");
});
```

#### Event Phases

## Asynchronous JavaScript

### JavaScript Promises

You can think of Promises as a special function that either satisfy (`resolve`) or fail (`reject`) to execute a task, and then executes the corresponding actions, usually another task with the returned data in the case of 'resolved' and usually throw an error in the case of 'reject'.

```javascript
var promise = new Promise(function(resolve, reject) {
  // do a thing, possibly async, then…

  if (/* everything turned out fine */) {
    resolve("Stuff worked!");
  }
  else {
    reject(Error("It broke"));
  }
});
```

We can perform calculations in the if-else ladder and return some calculated values in the `resolve()` and `reject()` functions.

We can perform actions based on whether the promise resolved or fails and gets rejected with a `then()` and `catch()` respectively.

```javascript
let promise = new Promise((resolve, reject) => {
  /*
  .
  ..
  do all the tasks that are required
  ..
  .
  */

  // resolve or reject depending on the result
  if (valueSuccessful) {
    // do actions on success
    // with valueSuccessful
    resolve(resolvedSuccessValue);
  } else {
    // do actions on failure
    // with valueFailed
    reject(rejectedFailureValue);
  }
});

promise
  .then(resolvedSuccessValue => {
    // do some actions with
    // resolvedSuccessValue
    console.log("Successful : " + resolvedSuccessValue);
  })
  .catch(rejectedFailureValue => {
    // do some actions with
    // rejectedFailureValue
    console.log("Fail : " + rejectedFailureValue);
  });
```

#### Running Promises in Parallel

We can initiate multiple promises to run at the same time and then do some task after all the promises have got resolved/rejected.

```javascript
const taskOne = new Promise((resolve, reject) => {
  resolve("taskOne Success!");
});

const taskTwo = new Promise((resolve, reject) => {
  resolve("taskTwo Success!");
});

const taskThree = new Promise((resolve, reject) => {
  resolve("taskThree Success!");
});

const taskFour = new Promise((resolve, reject) => {
  resolve("taskFour Success!");
});

const taskFive = new Promise((resolve, reject) => {
  resolve("taskFive Success!");
});

Promise.all([taskOne, taskTwo, taskThree, taskFour, taskFive]).then(
  messages => {
    console.log(messages);
  }
);

// o/p : ["taskOne Success!", "taskTwo Success!", "taskThree Success!", "taskFour Success!", "taskFive Success!"]
```

In the code snippet above we have five promises that have been been initiated together with the `Promise.all()` function call.

The general syntax is as follows:

```javascript
Promise.all([array, of, promises])
  .then(arrayOfResolveValues => {
    // some actions on arrayOfResolveValues
    console.log(arrayOfResolveValues);
  })
  .catch(arrayOfRejectValues => {
    console.log(arrayOfRejectValues);
  });
```

If you have n number of promises and even one fails then the catch block will be executed. When one task fails then all the execution of all the ongoing promises is stopped.

So, in the code block above if one of the tasks gets rejected, then the catch statement will be activated.

```javascript
const taskOne = new Promise((resolve, reject) => {
  resolve("taskOne Success!");
});

const taskTwo = new Promise((resolve, reject) => {
  resolve("taskTwo Success!");
});

const taskThree = new Promise((resolve, reject) => {
  resolve("taskThree Success!");
});

const taskFour = new Promise((resolve, reject) => {
  resolve("taskFour Success!");
});

// CHANGE - taskFive fails and is rejected
const taskFive = new Promise((resolve, reject) => {
  reject("taskFive FAIL!");
});

Promise.all([taskOne, taskTwo, taskThree, taskFour, taskFive])
  .then(messages => {
    console.log(messages);
  })
  .catch(messages => {
    console.log(messages);
  });

// o/p : ["taskFive FAIL!"]
```
