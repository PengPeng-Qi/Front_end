## JS Browser BOM
The **B**rowser **O**bject **M**odel (BOM) allows JavaScript to "talk to" the browser.  

### <a name="index"/>Connect 
- [JavaScript Window - The Browser Object Model](#Window)  
- [JavaScript Window Screen](#Screen)  
- [JavaScript Window Location](#location)  
- [](#)
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
