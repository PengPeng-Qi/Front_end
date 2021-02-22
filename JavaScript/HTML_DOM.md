## HTML DOM 
<b>The HTML DOM is a standard for how to get, change, add, or delete HTML elements.</b>

The W3C DOM standard is separated into 3 different parts:

* Core DOM - standard model for all document types  
* XML DOM - standard model for XML documents  
* HTML DOM - standard model for HTML documents  
### Finding HTMl Elements
* Finding HTML elements by id  
* Finding HTML elements by tag name  
* Finding HTML elements by class name  
* Finding HTML elements by CSS selectors  
* Finding HTML elements by HTML object collections  

example finds the element with id="intro":  
var myElement = document.getElementById("intro");

example finds all `<p>` elements:
document.getElementsByTagName("p")  
  
This example returns a list of all elements with class="intro".  
document.getElementsByClassName("intro")  
  
This example returns a list of all `<p>` elements with class="intro".  
document.querySelectorAll("p.intro")  
<hr>
<b>he following HTML objects (and object collections) are also accessible:</b>

* document.anchors  
* document.body  
* document.documentElement  
* document.embeds  
* document.forms  
* document.head  
* document.images  
* document.links  
* document.scripts  
* document.title  
### HTML DOM - Changing HTML
##### Changing the HTML Output Stream
document.write() can be used to write directly to the HTML output stream:  
```html
<script>
    document.write(Date());
</script>
```
> Never use document.write() after the document is loaded. It will overwrite the document.  

##### Changing HTML Content
To change the content of an HTML element, use this syntax:  
```html
// document.getElementById(id).innerHTML = new HTML
<p id="p1">Hello World!</p>

<script>
document.getElementById("p1").innerHTML = "New text!";
</script>
```
##### Changing the Value of an Attribute(属性)
To change the value of an HTML attribute, use this syntax: 
```html
// document.getElementById(id).attribute = new value

// This example changes the value of the src attribute of an <img> element:
<img id="myImage" src="smiley.gif">

<script>
document.getElementById("myImage").src = "landscape.jpg";
</script>
```
### HTML DOM - Changing CSS
##### Changing HTML Style
To change the style of an HTML element, use this syntax:
```html
// document.getElementById(id).style.property = new style

<p id="p2">Hello World!</p>

<script>
document.getElementById("p2").style.color = "blue";
</script>
```
##### Using Events
This example changes the style of the HTML element with id="id1", when the user clicks a button:
```html
<h1 id="id1">My Heading 1</h1>

<button type="button"
onclick="document.getElementById('id1').style.color = 'red'">
Click Me!</button>
```
[HTML DOM Style Object Reference.](https://www.w3schools.com/jsref/dom_obj_style.asp)
### HTML DOM Animation(动画)
##### A Basic Web Page
To demonstrate how to create HTML animations with JavaScript, we will use a simple web page:  
```html
<!DOCTYPE html>
<html>
<body>

<h1>My First JavaScript Animation</h1>

<div id="animation">My animation will go here</div>

</body>
</html>
```
##### Create an Animation Container
All animations should be relative to a container element.
```html
 <div id ="container">
  <div id ="animate">My animation will go here</div>
</div> 
```
##### Style the Elements
The container element should be created with style = "position: relative(相对的)".  
  
The animation element should be created with style = "position: absolute(绝对的)".  
  
```css
#container {
  width: 400px;
  height: 400px;
  position: relative;
  background: yellow;
}
#animate {
  width: 50px;
  height: 50px;
  position: absolute;
  background: red;
}
```
##### Animation Code
JavaScript animations are done by programming <b>gradual changes</b> in an element's style.  
```js
var id = setInterval(frame, 5);

function frame() {
  if (/* test for finished */) {
    clearInterval(id);
  } else {
    /* code to change the element style */ 
  }
}
```
[Example_Animation](https://www.w3schools.com/js/tryit.asp?filename=tryjs_dom_animate_3)
### HTML DOM Events
##### Reacting to Events
To execute code when a user clicks on an element, add JavaScript code to an HTML event attribute:  
```
onclick=JavaScript
```
  
Examples of HTML events:  

* When a user clicks the mouse  
* When a web page has loaded  
* When an image has been loaded  
* When the mouse moves over an element  
* When an input field is changed  
* When an HTML form is submitted  
* When a user strokes a key  
  
In this example, the content of the `<h1>` element is changed when a user clicks on it:
```html
<h1 onclick="this.innerHTML = 'Ooops!'">Click on this text!</h1>
<!-- 或者这样 -->
<h1 onclick="changeText(this)">Click on this text!</h1>

<script>
function changeText(id) {
  id.innerHTML = "Ooops!";
}
</script>
```
To assign events to HTML elements you can use event attributes.
```html
<button onclick="displayDate()">Try it</button> 
```
The HTML DOM allows you to assign events to HTML elements using JavaScript,a function named displayDate will be executed when the button is clicked.   
```html
 <script>
document.getElementById("myBtn").onclick = displayDate;
</script> 
```
##### The onload and onunload Events
The <b>onload and onunload</b> events are triggered when the user enters or leaves the page.  
  
The onload event can be used to check the visitor's browser type and browser version, and load the proper version of the web page based on the information.  
  
The onload and onunload events can be used to deal with cookies.  
```html
<body onload="checkCookies()"> 
```
##### The onchange Event
The <b>onchange</b> event is often used in combination with validation(确认) of input fields.  
  
Below is an example of how to use the onchange. The **upperCase()** function will be called when a user changes the content of an input field.
```html
<input type="text" id="fname" onchange="upperCase()"> 
```
##### The onmouseover and onmouseout Events
The onmouseover and onmouseout events can be used to trigger a function when the user mouses over, or out of, an HTML element:
```html
<div onmouseover="mOver(this)" onmouseout="mOut(this)" 
style="background-color:#D94A38;width:120px;height:20px;padding:40px;">
Mouse Over Me</div>

<script>
function mOver(obj) {
  obj.innerHTML = "Thank You"
}

function mOut(obj) {
  obj.innerHTML = "Mouse Over Me"
}
</script>

```
##### The onmousedown, onmouseup and onclick Events
The onmousedown, onmouseup, and onclick events are all parts of a mouse-click.
```html
<div onmousedown="mDown(this)" onmouseup="mUp(this)"
style="background-color:#D94A38;width:90px;height:20px;padding:40px;">
Click Me</div>

<script>
function mDown(obj) {
  obj.style.backgroundColor = "#1ec5e5";
  obj.innerHTML = "Release Me";
}

function mUp(obj) {
  obj.style.backgroundColor="#D94A38";
  obj.innerHTML="Thank You";
}
</script>
```
[HTML DOM Event Object Reference](https://www.w3schools.com/jsref/dom_obj_event.asp)
### HTML DOM EventListener
##### Syntax
```
element.addEventListener(event, function, useCapture);
```
  
The first parameter is the type of the event (like **"click" or "mousedown"** or any other [HTML DOM Event.](https://www.w3schools.com/jsref/dom_obj_event.asp))  
  
The second parameter is the function we want to call when the event occurs.   
  
The third parameter is a boolean value specifying whether to use event bubbling or event capturing. This parameter is optional.  
> Note that you don't use the "on" prefix for the event; <b>use "click" instead of "onclick".</b>

##### Add an Event Handler to an Element  
Alert "Hello World!" when the user clicks on an element:
```js
element.addEventListener("click", function(){ alert("Hello World!"); }); 
```
```js
element.addEventListener("click", myFunction);

function myFunction() {
  alert ("Hello World!");
} 
```
##### Add Many Event Handlers to the Same Element
The `addEventListener()` method allows you to add many events to the same element, without overwriting existing events:
```js
element.addEventListener("mouseover", myFunction);
element.addEventListener("click", mySecondFunction);
element.addEventListener("mouseout", myThirdFunction); 
```
##### Passing Parameters(参数)
```js
//element.addEventListener("click", function(){ myFunction(p1, p2); });

<script>
var p1 = 5;
var p2 = 7;

document.getElementById("myBtn").addEventListener("click", function() {
  myFunction(p1, p2);
});

function myFunction(a, b) {
  var result = a * b;
  document.getElementById("demo").innerHTML = result;
}
</script>
```
##### Event Bubbling(冒泡) or Event Capturing(俘获)?
There are two ways of event propagation in the HTML DOM, bubbling and capturing.  
  
In bubbling the inner most element's event is handled first and then the outer:  

In capturing the outer most element's event is handled first and then the inner:  
  
```
addEventListener(event, function, useCapture);
```
The default value is false, which will use the bubbling propagation, when the value is set to true, the event uses the capturing propagation.  
  
```js
document.getElementById("myP").addEventListener("click", myFunction, true);
document.getElementById("myDiv").addEventListener("click", myFunction, true);
```
##### The removeEventListener() method
The removeEventListener() method removes event handlers that have been attached with the addEventListener() method:  
```
element.removeEventListener("mousemove", myFunction); 
```
### HTML DOM Navigation(导航)
##### DOM Nodes
According to the W3C HTML DOM standard, everything in an HTML document is a node:  
  
* The entire document is a document node  
* Every HTML element is an element node  
* The text inside HTML elements are text nodes  
* Every HTML attribute is an attribute(属性) node (deprecated(不赞同))--(不建议使用)  
* All comments are comment(评论) nodes(例如注释符号)  
##### Navigating Between Nodes
You can use the following node properties to navigate between nodes with JavaScript:  
  
* parentNode  
* childNodes[nodenumber]  
* firstChild  
* lastChild  
* nextSibling  
* previousSibling  
