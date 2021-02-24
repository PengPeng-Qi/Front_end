## JS Browser BOM
The **B**rowser **O**bject **M**odel (BOM) allows JavaScript to "talk to" the browser.  

### <a name="index"/>Connect 
- [JavaScript Window - The Browser Object Model](#Window)  
- [JavaScript Window Screen](#Screen)  
- [JavaScript Window Location](#location)  
- [JavaScript Window History](#History)  
- [JavaScript Window Navigator](#Navigator)  
- [JavaScript Popup Boxes](#Popup)  
- [JavaScript Timing Events](#Timing)  
- [JavaScript Cookies](#Cookies)  
### <a name="Window"/>JavaScript Window - The Browser Object Model 
##### The Window Object
The document object (of the HTML DOM) is a property of the window object:
```js
window.document.getElementById("header"); 
```
is the same as:
```js
document.getElementById("header"); 
```
##### Window Size
Two properties(属性) can be used to determine the size of the browser window.  

Both properties return the sizes in pixels:  

* <b>window.innerHeight</b> - the inner height of the browser window (in pixels)  
* <b>window.innerWidth</b> - the inner width of the browser window (in pixels)
  
> The browser window (the browser viewport) is NOT including toolbars(工具栏) and scrollbars(滚动条).  
  
For Internet Explorer 8, 7, 6, 5:  

* document.documentElement.clientHeight  
* document.documentElement.clientWidth  

or  

* document.body.clientHeight  
* document.body.clientWidth  
  
##### Other Window Methods
Some other methods:  

- <b>window.open()</b> - open a new window  
- <b>window.close()</b> - close the current window  
- <b>window.moveTo()</b> - move the current window  
- <b>window.resizeTo()</b> - resize the current window  
### <a name="Screen"/>JavaScript Window Screen
##### Window Screen
The `window.screen` object can be written without the window prefix.  

Properties:  

- <b>screen.width</b>  
- <b>screen.height</b>  
- <b>screen.availWidth</b>  
- <b>screen.availHeight</b>  
- <b>screen.colorDepth</b>  
- <b>screen.pixelDepth</b>  
##### Window Screen Width/Height
Display the width/height of the screen in pixels:
```js
// Screen Width
document.getElementById("demo").innerHTML =
"Screen Width: " + screen.width;

// Screen Height
document.getElementById("demo").innerHTML =
"Screen Height: " + screen.height;
```
##### Window Screen Available Width/Height
The screen.availWidth property returns the width of the visitor's screen, in pixels, minus(减去) interface(界面) features like the Windows Taskbar(任务栏).
```js
// Available Screen Width: 1920 
document.getElementById("demo").innerHTML =
"Available Screen Width: " + screen.availWidth;

// Available Screen Height: 1030 
document.getElementById("demo").innerHTML =
"Available Screen Height: " + screen.availHeight;
```
##### Window Screen Color Depth
The `screen.colorDepth` property returns the number of bits used to display one color.  
  
All modern computers use 24 bit or 32 bit hardware for color resolution:  

* 24 bits =      16,777,216 different "True Colors"  
* 32 bits = 4,294,967,296 different "Deep Colors"  
  
Older computers used 16 bits: 65,536 different "High Colors" resolution.  
  
Very old computers, and old cell phones used 8 bits: 256 different "VGA colors".  
```js
document.getElementById("demo").innerHTML =
"Screen Color Depth: " + screen.colorDepth;

// Screen Color Depth: 24 
```
##### Window Screen Pixel Depth
The `screen.pixelDepth` property returns the pixel depth of the screen.
```js
document.getElementById("demo").innerHTML =
"Screen Pixel Depth: " + screen.pixelDepth;

// Screen Pixel Depth: 24 
```
> For modern computers, Color Depth and Pixel Depth are equal.

### <a name="Location"/>JavaScript Window Location
The `window.location` object can be used to get the current page address (URL) and to redirect the browser to a new page.
##### Window Location
The `window.location` object can be written without the window prefix(前缀).  
  
Some examples:  
  
* <b>window.location.href</b> returns the href (URL) of the current page  
* <b>window.location.hostname</b> returns the domain name of the web host  
* <b>window.location.pathname</b> returns the path and filename of the current page  
* <b>window.location.protocol</b> returns the web protocol used (http: or https:)  
* <b>window.location.assign()</b> loads a new document  

##### Window Location Href
The `window.location.href` property returns the URL of the current page.
```js
document.getElementById("demo").innerHTML =
"Page location is " + window.location.href;

// Page location is https://www.w3schools.com/js/js_window_location.asp 
```
##### Window Location Hostname
The `window.location.hostname` property returns the name of the internet host (of the current page).
```js
document.getElementById("demo").innerHTML =
"Page hostname is " + window.location.hostname;

// Page hostname is www.w3schools.com 
```
##### Window Location Pathname
The `window.location.pathname` property returns the pathname of the current page.
```js
document.getElementById("demo").innerHTML =
"Page path is " + window.location.pathname;

// Page path is /js/js_window_location.asp
```
##### Window Location Protocol
The `window.location.protocol` property returns the web protocol of the page.
```js
document.getElementById("demo").innerHTML =
"Page protocol is " + window.location.protocol;

// Page protocol is https: 
```
##### Window Location Port
The `window.location.port` property returns the number of the internet host port (of the current page).
```js
document.getElementById("demo").innerHTML =
"Port number is " + window.location.port; 

// Port number is 
// Note: If the port number is default (80 for http and 443 for https), most browsers will display 0 or nothing.
```
##### Window Location Assign
The `window.location.assign()` method loads a new document.
```html
<head>
<script>
function newDoc() {
  window.location.assign("https://www.w3schools.com")
}
</script>
</head>
<body>

<input type="button" value="Load new document" onclick="newDoc()">

</body>
```
### <a name="History"/>JavaScript Window History
The `window.history` object contains(包含) the browsers history.  
##### Window History
The `window.history` object can be written without the window prefix(前缀).  
  
To protect the privacy of the users, there are limitations to how JavaScript can access this object.  
  
Some methods:  
  
* <b>history.back()</b> - same as clicking back in the browser  
* <b>history.forward()</b> - same as clicking forward in the browser  
##### Window History Back
The `history.back()` method loads the previous URL in the history list.  
```html
<head>
<script>
    function goBack() {
      window.history.back()
    }
</script>
</head>
<body>

<input type="button" value="Back" onclick="goBack()">

</body>
```
##### Window History Forward
The `history.forward()` method loads the next URL in the history list.  
  
This is the same as clicking the Forward button in the browser.  
```html
<head>
<script>
    function goForward() {
      window.history.forward()
    }
</script>
</head>
<body>

<input type="button" value="Forward" onclick="goForward()">

</body>
</html>
```
### <a name="Navigator"/>JavaScript Window Navigator
The `window.navigator` object contains information about the visitor's browser.
##### Window Navigator
The `window.navigator` object can be written without the window prefix.  
  
Some examples:  
  
* navigator.appName  
* navigator.appCodeName  
* navigator.platform  

##### Browser Cookies
The `cookieEnabled` property returns true if cookies are enabled, otherwise false:
```html
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML =
"cookiesEnabled is " + navigator.cookieEnabled;
</script>

//  navigator.cookieEnabled is true
```
##### Browser Application Name
The `appName` property returns the application name of the browser:
```html
<p id="demo"></p>

<script>
    document.getElementById("demo").innerHTML =
    "navigator.appName is " + navigator.appName;
</script> 

// navigator.appName is Netscape
```
> Strange enough, "Netscape" is the application name for both IE11, Chrome, Firefox, and Safari.

##### Browser Application Code Name
The `appCodeName` property returns the application code name of the browser:
```html
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML =
"navigator.appCodeName is " + navigator.appCodeName;
</script> 

// navigator.appCodeName is Mozilla
```
> "Mozilla" is the application code name for both Chrome, Firefox, IE, Safari, and Opera.

##### The Browser Engine
The `product` property returns the product name of the browser engine:
```html
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML =
"navigator.product is " + navigator.product;
</script> 

// navigator.product is Gecko
```
> Do not rely on this. Most browsers returns "Gecko" as product name !!

##### The Browser Version
The `appVersion` property returns version information about the browser:
```html
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = navigator.appVersion;
</script> 

// 5.0 (Windows)
```
##### The Browser Agent
The `userAgent` property returns the user-agent header sent by the browser to the server:
```html
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = navigator.userAgent;
</script> 

// Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:86.0) Gecko/20100101 Firefox/86.0
```
##### The Browser Platform
The `platform` property returns the browser platform (operating system)(操作系统):  
```html
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = navigator.platform;
</script> 

// navigator.platform is Win32
```
##### The Browser Language
The `language` property returns the browser's language:
```html
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = navigator.language;
</script> 

// navigator.language is zh-CN
```
##### Is The Browser Online?
The `onLine` property returns true if the browser is online:
```html
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = navigator.onLine;
</script> 

// navigator.onLine is true
```
##### Is Java Enabled?
The `javaEnabled()` method returns true if Java is enabled:
```html
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = navigator.javaEnabled();
</script> 

// javaEnabled is false
```
### <a name="Popup"/>JavaScript Popup(弹出) Boxes(盒子)
JavaScript has three kind of popup boxes: Alert box, Confirm(确认) box, and Prompt(提示) box.
##### Alert Box
An alert box is often used if you want to make sure information comes through to the user.  
  
When an alert box pops up, the user will have to click "OK" to proceed.   
  
```js
window.alert("sometext");
```
> The window.alert() method can be written without the window prefix.

```js
alert("I am an alert box!");
```
##### Confirm Box
A confirm box is often used if you want the user to verify(核实) or accept something.  

When a confirm box pops up, the user will have to click either "OK" or "Cancel" to proceed.  
  
If the user clicks "OK", the box returns true. If the user clicks "Cancel", the box returns false.  
```js
window.confirm("sometext");
```
>The `window.confirm()` method can be written without the window prefix.

```html
<h2>JavaScript Confirm Box</h2>


<button onclick="myFunction()">Try it</button>

<p id="demo"></p>

<script>
function myFunction() {
  var txt;
  if (confirm("Press a button!")) {
    txt = "You pressed OK!";
  } else {
    txt = "You pressed Cancel!";
  }
  document.getElementById("demo").innerHTML = txt;
}
</script>
```
##### Prompt(提示) Box
A prompt box is often used if you want the user to input a value before entering a page.
```js
window.prompt("sometext","defaultText");
```
> The window.prompt() method can be written without the window prefix.

```js
var person = prompt("Please enter your name", "Harry Potter");

if (person == null || person == "") {
  txt = "User cancelled the prompt.";
} else {
  txt = "Hello " + person + "! How are you today?";
} 
```
##### Line Breaks
To display line breaks inside a popup box, use a back-slash followed by the character n.
```js
alert("Hello\nHow are you?");
```
### <a name="Timing"/>JavaScript Timing(定时、时间选择) Events
JavaScript can be executed(执行) in time-intervals(间隔).  
  
This is called timing events.  
##### Timing Events
The `window` object allows execution of code at specified time intervals.  
  
These time intervals are called timing events.  
  
The two key methods to use with JavaScript are:  
  
* `setTimeout(function, milliseconds(毫秒))` Executes a function, after waiting a specified number of milliseconds.  
* `setInterval(function, milliseconds)` Same as `setTimeout()`, but repeats the execution of the function continuously(连续不断的).  
> The <b>setTimeout()</b> and <b>setInterval()</b> are both methods of the HTML DOM Window object.

##### The setTimeout() Method
```js
window.setTimeout(function, milliseconds);
```
>The window.setTimeout() method can be written without the window prefix.

```html
<button onclick="setTimeout(myFunction, 3000)">Try it</button>

<script>
function myFunction() {
  alert('Hello');
}
</script> 
```
##### How to Stop the Execution(执行)?
The `clearTimeout()` method stops the execution of the function specified in setTimeout().
```js
window.clearTimeout(timeoutVariable)
```
>The window.clearTimeout() method can be written without the window prefix.

The `clearTimeout()` method uses the variable returned from `setTimeout()`:
```js
myVar = setTimeout(function, milliseconds);
clearTimeout(myVar);
```
If the function has not already been executed, you can stop the execution by calling the clearTimeout() method:
```html
<button onclick="myVar = setTimeout(myFunction, 3000)">Try it</button>

<button onclick="clearTimeout(myVar)">Stop it</button>
```
##### The setInterval()(间隔) Method
The `setInterval()` method repeats(反复) a given function at every given time-interval.
```js
window.setInterval(function, milliseconds);
```
>The window.setInterval() method can be written without the window prefix.

Display the current time:
```js
var myVar = setInterval(myTimer, 1000);

function myTimer() {
  var d = new Date();
  document.getElementById("demo").innerHTML = d.toLocaleTimeString();
} 
```
>There are 1000 milliseconds in one second.

### <a name="Cookies"/>JavaScript Cookies
Cookies let you store(储备) user information in web pages.  
##### What are Cookies?
Cookies are data, stored in small text files, on your computer.  
  
When a web server has sent a web page to a browser, the connection is shut down, and the server forgets everything about the user.  
  
Cookies were invented to solve the problem "how to remember information about the user":  
  
* When a user visits a web page, his/her name can be stored in a cookie.  
* Next time the user visits the page, the cookie "remembers" his/her name.  
  
Cookies are saved in name-value pairs like:  
```
username = John Doe 
```

##### Create a Cookie with JavaScript
JavaScript can create, read, and delete cookies with the `document.cookie` property.  
  
With JavaScript, a cookie can be created like this:  
```js
document.cookie = "username=John Doe"; 
```
You can also add an expiry(到期) date (in UTC time). By default, the cookie is deleted when the browser is closed:  
```js
document.cookie = "username=John Doe; expires=Thu, 18 Dec 2013 12:00:00 UTC"; 
```
With a path parameter(参数), you can tell the browser what path the cookie belongs to. By default, the cookie belongs to the current page.
```js
document.cookie = "username=John Doe; expires=Thu, 18 Dec 2013 12:00:00 UTC; path=/"; 
```
##### Read a Cookie with JavaScript
With JavaScript, cookies can be read like this:
```js
var x = document.cookie; 
```
> document.cookie will return all cookies in one string much like: cookie1=value; cookie2=value; cookie3=value;

##### Change a Cookie with JavaScript
With JavaScript, you can change a cookie the same way as you create it:
```js
document.cookie = "username=John Smith; expires=Thu, 18 Dec 2013 12:00:00 UTC; path=/";
```
> The old cookie is overwritten.

##### Delete a Cookie with JavaScript
Deleting a cookie is very simple.  
  
You don't have to specify(指定) a cookie value when you delete a cookie.  
  
Just set the `expires` parameter(参数) to a passed date:  
  
```js
document.cookie = "username=; expires=Thu, 01 Jan 1970 00:00:00 UTC; path=/;";
```
> You should define the cookie path to ensure that you delete the right cookie 
> Some browsers will not let you delete a cookie if you don't specify the path.

##### The Cookie String
The `document.cookie` property looks like a normal text string. But it is not.  
  
If you set a new cookie, older cookies are not overwritten. The new cookie is added to `document.cookie`, so if you read `document.cookie` again you will get something like:  
```
cookie1 = value; cookie2 = value;
```
If you want to find the value of one specified(指定) cookie, you must write a JavaScript function that searches for the cookie value(值) in the cookie string.  
##### JavaScript Cookie Example
In the example to follow, we will create a cookie that stores the name of a visitor.  
  
The first time a visitor arrives to the web page, he/she will be asked to fill in his/her name. The name is then stored in a cookie.  
  
The next time the visitor arrives at the same page, he/she will get a welcome message.  
  
For the example we will create 3 JavaScript functions:  
<ol>
    <li>A function to set a cookie value</li>
    <li>A function to get a cookie value</li>
    <li>A function to check a cookie value</li>
</ol>
<p><b>A Function to Set a Cookie</b></p>
First, we create a **function** that stores the name of the visitor in a cookie variable:
```js
function setCookie(cname, cvalue, exdays) {
  var d = new Date();
  d.setTime(d.getTime() + (exdays*24*60*60*1000));
  var expires = "expires="+ d.toUTCString();
  document.cookie = cname + "=" + cvalue + ";" + expires + ";path=/";
}
```
The parameters(参数) of the function above are the name of the cookie (cname), the value of the cookie (cvalue), and the number of days until the cookie should expire(过期) (exdays).  
<p><b>A Function to Get a Cookie</b></p>
Then, we create a function that returns the value of a specified cookie:  
```js
function getCookie(cname) {
  var name = cname + "=";
  var decodedCookie = decodeURIComponent(document.cookie);
  var ca = decodedCookie.split(';');
  for(var i = 0; i <ca.length; i++) {
    var c = ca[i];
    while (c.charAt(0) == ' ') {
      c = c.substring(1);
    }
    if (c.indexOf(name) == 0) {
      return c.substring(name.length, c.length);
    }
  }
  return "";
}

// 把 cookie 作为参数（cname）。

// 创建变量（name）与要搜索的文本（CNAME”=”）。

// 解码 cookie 字符串，处理带有特殊字符的 cookie，例如 “$”。

// 用分号把 document.cookie 拆分到名为 ca（decodedCookie.split(';')）的数组中。

// 遍历 ca 数组（i = 0; i < ca.length; i++），然后读出每个值 c = ca[i]。

// 如果找到 cookie（c.indexOf(name) == 0），则返回该 cookie 的值（c.substring(name.length, c.length）。

// 如果未找到 cookie，则返回 ""。
```
<p><b>A Function to Check a Cookie</b></p>
Last, we create the function that checks if a cookie is set.  
  
If the cookie is set it will display a greeting.  
  
If the cookie is not set, it will display a prompt box, asking for the name of the user, and stores the username cookie for 365 days, by calling the setCookie function:  
```js
function checkCookie() {
  var username = getCookie("username");
  if (username != "") {
   alert("Welcome again " + username);
  } else {
    username = prompt("Please enter your name:", "");
    if (username != "" && username != null) {
      setCookie("username", username, 365);
    }
  }
}

```
##### All Together Now
```js
function setCookie(cname, cvalue, exdays) {
  var d = new Date();
  d.setTime(d.getTime() + (exdays * 24 * 60 * 60 * 1000));
  var expires = "expires="+d.toUTCString();
  document.cookie = cname + "=" + cvalue + ";" + expires + ";path=/";
}

function getCookie(cname) {
  var name = cname + "=";
  var ca = document.cookie.split(';');
  for(var i = 0; i < ca.length; i++) {
    var c = ca[i];
    while (c.charAt(0) == ' ') {
      c = c.substring(1);
    }
    if (c.indexOf(name) == 0) {
      return c.substring(name.length, c.length);
    }
  }
  return "";
}

function checkCookie() {
  var user = getCookie("username");
  if (user != "") {
    alert("Welcome again " + user);
  } else {
    user = prompt("Please enter your name:", "");
    if (user != "" && user != null) {
      setCookie("username", user, 365);
    }
  }
} 
```
>The example above runs the checkCookie() function when the page loads.