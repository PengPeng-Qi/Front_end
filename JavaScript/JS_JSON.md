## JS_JSON
### <a name="index"/>Contents
- [JSON - Introduction](#Introduction)  
- [JSON Syntax](#Syntax)  
- [JSON vs XML](#XML)  
- [JSON.parse()](#parse)  
- [JSON.stringify()](#stringify)  
- [JSON PHP](https://www.w3schools.com/js/js_json_php.asp)  
- [JSON HTML](https://www.w3schools.com/js/js_json_html.asp)  
- [JSONP](https://www.w3schools.com/js/js_json_jsonp.asp)
  
### <a name="Introduction"/>JSON - Introduction
<div style="background-color: #8FBC8F; padding: 25px 50px;">
    <p>JSON: <b>J</b>avaScript <b>O</b>bject <b>N</b>otation.(符号)</p>
    <p>JSON is a syntax(语法) for storing and exchanging data.</p>
    <p>JSON is text, written with JavaScript object notation.</p>
</div>
##### Exchanging Data
When exchanging data between a browser and a server, the data can only be text.  
  
JSON is text, and we can convert(转变) any JavaScript object into JSON, and send JSON to the server.  
### <a name="Syntax">JSON Syntax
The JSON syntax is a subset(子集) of the JavaScript syntax.  
  
* Data is in name/value pairs  
* Data is separated by commas(逗号)  
* Curly(弯曲的) braces hold objects  
* Square(直的) brackets(括号) hold arrays  

##### JSON Data - A Name and a Value
```js
 "name":"John" 
```
>JSON names require double quotes. JavaScript names don't.

##### JSON Values
In <b>JSON</b>, <span style="font-style: italic;">values</span> must be one of the following data types:  
  
* a string  
* a number  
* an object (JSON object)  
* an array  
* a boolean  
* null  
  
```json
{ "name":"John", 
  "age":30, 
  "employee":{ "name":"John", "age":30, "city":"New York" }, 
  "employees":[ "John", "Anna", "Peter" ],
  "sale":true,
  "middlename":null,
} 
```

In **JavaScript** values can be all of the above, plus any other valid JavaScript expression, including:  

* a function  
* a date  
* undefined  
  
In JSON, string values must be written with double quotes:  
  
```js
{ "name":"John" }
```

##### JSON Files
* The file type for JSON files is ".json"  
* The MIME type for JSON text is "application/json"  
### <a name="XML"/>JSON vs XML  
Both JSON and XML can be used to receive(接收) data from a web server.  
  
JSON Example:  
```js
{"employees":[
  { "firstName":"John", "lastName":"Doe" },
  { "firstName":"Anna", "lastName":"Smith" },
  { "firstName":"Peter", "lastName":"Jones" }
]}
```
XML Example:  
```xml
<employees>
  <employee>
    <firstName>John</firstName> <lastName>Doe</lastName>
  </employee>
  <employee>
    <firstName>Anna</firstName> <lastName>Smith</lastName>
  </employee>
  <employee>
    <firstName>Peter</firstName> <lastName>Jones</lastName>
  </employee>
</employees>
```
### <a name="parse"/>JSON.parse()
When receiving data from a web server, the data is always a string.  
  
Parse the data with <span style="color: red;">`JSON.parse()`</span>, and the data becomes a JavaScript object.  
  
```js
// Imagine we received this text from a web server:
'{ "name":"John", "age":30, "city":"New York"}'

// Use the JavaScript function JSON.parse() to convert text into a JavaScript object:
var obj = JSON.parse('{ "name":"John", "age":30, "city":"New York"}'); 
// Make sure the text is written in JSON format, or else you will get a syntax error.
```
##### JSON From the Server
You can request JSON from the server by using an AJAX request  
  
As long as the response from the server is written in JSON format, you can parse the string into a JavaScript object.   
  
Use the `XMLHttpRequest` to get data from the server:  
  
```js
var xmlhttp = new XMLHttpRequest();
xmlhttp.onreadystatechange = function() {
  if (this.readyState == 4 && this.status == 200) {
    var myObj = JSON.parse(this.responseText);
    document.getElementById("demo").innerHTML = myObj.name;
  }
};
xmlhttp.open("GET", "json_demo.txt", true);
xmlhttp.send(); 
```
##### Array as JSON
When using the <span style="color: red;">`JSON.parse()`</span> on a JSON derived from an array, the method will return a JavaScript array, instead of a JavaScript object.

##### Exceptions
Parsing Dates  
  
**Date objects** are not allowed in JSON.  
  
If you need to include a date, write it as a string.  
  
You can convert it back into a date object later:  
  
```js
var text = '{ "name":"John", "birth":"1986-12-14", "city":"New York"}';
var obj = JSON.parse(text);
obj.birth = new Date(obj.birth);

document.getElementById("demo").innerHTML = obj.name + ", " + obj.birth; 
```
Or, you can use the second parameter, of the JSON.parse() function, called reviver.  
```js
var text = '{ "name":"John", "birth":"1986-12-14", "city":"New York"}';
var obj = JSON.parse(text, function (key, value) {
  if (key == "birth") {
    return new Date(value);
  } else {
    return value;
  }
});

document.getElementById("demo").innerHTML = obj.name + ", " + obj.birth; 
```
Functions are not allowed in JSON.  
  
If you need to include a function, write it as a string.  
  
```js
var text = '{ "name":"John", "age":"function () {return 30;}", "city":"New York"}';
var obj = JSON.parse(text);
obj.age = eval("(" + obj.age + ")");

document.getElementById("demo").innerHTML = obj.name + ", " + obj.age(); 
```
>You should avoid using functions in JSON, the functions will lose their scope, and you would have to use <span style="color: red;">eval()</span> to convert them back into functions.

###  <a name="stringify">JSON.stringify()
A common use of JSON is to exchange data to/from a web server.  
  
When sending data to a web server, the data has to be a string.  
  
Convert a JavaScript object into a string with <span style="color: red">`JSON.stringify().`</span>  
  
##### Stringify a JavaScript Object
```js
var obj = { name: "John", age: 30, city: "New York" };
var myJSON = JSON.stringify(obj);
document.getElementById("demo").innerHTML = myJSON; 

// {"name":"John","age":30,"city":"New York"}
```
##### Stringify a JavaScript Array
It is also possible to stringify JavaScript arrays:  
  
```js
var arr = [ "John", "Peter", "Sally", "Jane" ];
var myJSON = JSON.stringify(arr);
document.getElementById("demo").innerHTML = myJSON; 

// ["John","Peter","Sally","Jane"]
```
##### Exceptions
**Stringify Dates**  
  
In JSON, date objects are not allowed. The <span style="color: red;">`JSON.stringify()`</span> function will convert any dates into strings.  
  
```js
var obj = { name: "John", today: new Date(), city : "New York" };
var myJSON = JSON.stringify(obj);

document.getElementById("demo").innerHTML = myJSON; 

// {"name":"John","today":"2021-02-25T06:28:17.629Z","city":"New York"}
```
**Stringify Functions**  
  
In JSON, functions are not allowed as object values.  
  
The <span style="color: red;">`JSON.stringify()`</span> function will **remove any functions from a JavaScript object**, both the key and the value:  
  
```js
var obj = { name: "John", age: function () {return 30;}, city: "New York"};
var myJSON = JSON.stringify(obj);

document.getElementById("demo").innerHTML = myJSON; 

// {"name":"John","city":"New York"}
```
This can be omitted(省略) if you convert your functions into strings before running the <span style="color: red;">`JSON.stringify()`</span> function.  
  
```js
var obj = { name: "John", age: function () {return 30;}, city: "New York" };
obj.age = obj.age.toString();
var myJSON = JSON.stringify(obj);

document.getElementById("demo").innerHTML = myJSON; 

// {"name":"John","age":"function () {return 30;}","city":"New York"}
```