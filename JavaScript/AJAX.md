## AJAX
### <a name="index"/>Contents
- [AJAX Introduction](#Introduction)  
- [AJAX - The XMLHttpRequest Object](#XHR)  
- [AJAX - Send a Request To a Server](#Request)  
### <a name="Introduction"/>AJAX Introduction
AJAX is a developer's dream, because you can:  

* Read data from a web server - after the page has loaded  
* Update a web page without reloading the page  
* Send data to a web server - in the background  

##### What is AJAX?
**AJAX** = **A**synchronous(异步的) **J**avaScript **A**nd **X**ML.  
  
AJAX is not a programming language.  
  
AJAX just uses a combination(组合) of:  
  
* A browser built-in <b>XMLHttpRequest</b> object (to request data from a web server)  
* JavaScript and HTML DOM (to display or use the data)  

>AJAX is a misleading(使人误解的) name. AJAX applications might use XML to transport data, but it is equally(相同的) common to transport data as plain(清晰的、简单的) text or JSON text.  

##### How AJAX Works
![How AJAX Works](https://raw.githubusercontent.com/PengPeng-Qi/Goodnotes/main/JavaScript/src/pic_ajax.png)
### <a name="XHR">AJAX - The XMLHttpRequest Object
The keystone(主旨) of AJAX is the XMLHttpRequest object. 
##### The XMLHttpRequest Object
All modern browsers support the `XMLHttpRequest` object.  
  
The `XMLHttpRequest` object can be used to exchange data with a web server behind the scenes. This means that it is possible to update parts of a web page, without reloading the whole page.  
##### Create an XMLHttpRequest Object
Syntax for creating an `XMLHttpRequest` object:
```js
variable = new XMLHttpRequest();
```
##### Access(访问) Across Domains(域名)(跨域访问)
For security reasons, modern browsers do not allow access across domains.  
  
This means that both the web page and the XML file it tries to load, must be located on the same server.  
##### Modern Browsers (Fetch(取得) API)
Modern Browsers can use Fetch API instead of the XMLHttpRequest Object.  
  
The Fetch API interface allows web browser to make HTTP requests to web servers.  
  
If you use the XMLHttpRequest Object, Fetch can do the same in a simpler way.  
##### Old Browsers (IE5 and IE6)
Old versions of Internet Explorer (5/6) use an ActiveX object instead of the `XMLHttpRequest` object:  
```js
variable = new ActiveXObject("Microsoft.XMLHTTP");
```
To handle IE5 and IE6, check if the browser supports the `XMLHttpRequest` object, or else create an `ActiveX` object:
```js
if (window.XMLHttpRequest) {
   // code for modern browsers
   xmlhttp = new XMLHttpRequest();
 } else {
   // code for old IE browsers
   xmlhttp = new ActiveXObject("Microsoft.XMLHTTP");
} 
```
##### XMLHttpRequest Object Methods
![XMLHttpRequest Object Methods](https://raw.githubusercontent.com/PengPeng-Qi/Goodnotes/main/JavaScript/src/XMLHttpRequest%E5%AF%B9%E8%B1%A1%E6%96%B9%E6%B3%95.PNG)
##### XMLHttpRequest Object Properties
![XMLHttpRequest Object Properties](https://raw.githubusercontent.com/PengPeng-Qi/Goodnotes/main/JavaScript/src/XMLHttpRequest%E5%AF%B9%E8%B1%A1%E5%B1%9E%E6%80%A7.PNG)
### <a name="Request"/>AJAX - Send a Request To a Server
##### Send a Request To a Server
To send a request to a server, we use the `open()` and `send()` methods of the `XMLHttpRequest` object:
```js
xhttp.open("GET", "ajax_info.txt", true);
xhttp.send();
```

<table>
    <thead>
        <tr>
            <th>Method</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody style="font-style: italic;">
        <tr style="background-color: #eee;">
            <td>open(method, url, async(异步))</td>
            <td>Specifies the type of request<br>
                <br>
                method: the type of request: GET or POST<br>
                url: the server (file) location<br>
                async: true (asynchronous) or false (synchronous)<br>
            </td>
        </tr>
        <tr>
            <td>send()</td>
            <td>Sends the request to the server (used for GET)</td>
        </tr>
        <tr style="background-color: #eee;">
            <td>send(string)</td>
            <td>Sends the request to the server (used for POST)</td>
        </tr>
    </tbody>
</table>
##### GET or POST?
<a style="color: red;">`GET`</a> is simpler and faster than <a style="color: red;">`POST`</a>, and can be used in most cases.  
  
However, always use POST requests when:  
  
* A cached(隐藏的) file is not an option (update a file or database on the server).  
* Sending a large amount of data to the server (POST has no size limitations).  
* Sending user input (which can contain unknown characters), POST is more robust(强健、健康的) and secure than GET.  
  
##### GET Requests
A simple <a style="color: red;">`GET`</a> request:  
  
```js
xhttp.open("GET", "demo_get.asp", true);
xhttp.send(); 
```
##### POST Requests
```js
xhttp.open("POST", "demo_post.asp", true);
xhttp.send(); 
```
To POST data like an HTML form, add an HTTP header with <a style="color: red;">`setRequestHeader()`</a>. Specify the data you want to send in the <a style="color: red;">`send()`</a> method: 
   
```js
xhttp.open("POST", "ajax_test.asp", true);
xhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
xhttp.send("fname=Henry&lname=Ford"); 
```