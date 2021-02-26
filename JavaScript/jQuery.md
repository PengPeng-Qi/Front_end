## jQuery
## <a name="index"/>Content
- [jQuery Tutorial](#Tutorial)  
- [jQuery Effects](#Effects)  
- [jQuery HTML](#HTML)  
- [jQuery Traversing](#Traversing)  
- [jQuery AJAX](#AJAX)  
- [jQuery Misc](#Misc)  
### <a name="Tutorial">jQuery Tutorial
### <a name="index"/>Contents
- [jQuery Tutorial](#JT)  
- [jQuery CDN](#CDN)  
- [jQuery Syntax](#Syntax)  
- [The Document Ready Event](#Event)  
- [jQuery Selectors](#Selectors)  
- [jQuery Event Methods](#Methods)  
#### <a name="JT">jQuery Tutoria(教程)
<dir style="background-color: #d4edda;border-left: none;padding: 32px;margin: 24px;margin-left: -32px;margin-right: -32px;">
    <p>jQuery is a JavaScript Library.</p>
    <p>jQuery greatly simplifies JavaScript programming.</p>
</dir>

#### <a name="CDN"/>jQuery CDN
If you don't want to download and host jQuery yourself, you can include it from a CDN (Content Delivery Network).  
  
```html
<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
</head> 
```
#### <a name="Syntax">jQuery Syntax
Basic syntax is: <span style="font-style: italic;"><b>$(selector).action()</b></span>
  
Examples:  
  
* <span style="color: red;">`$(this).hide()`</span> - hides the current element.  
  
* <span style="color: red;">`$("p").hide()`</span> - hides all `<p>` elements.  
  
* <span style="color: red;">`$(".test").hide()`</span> - hides all elements with class="test".  
  
* <span style="color: red;">`$("#test").hide()`</span> - hides the element with id="test".  
  
#### <a name="Event">The Document Ready Event
You might have noticed that all jQuery methods in our examples, are inside a document ready event:  
  
```js
$(document).ready(function(){

  // jQuery methods go here...

}); 
```
This is to prevent any jQuery code from running before the document is finished loading (is ready).
#### <a name="Selecctors">jQuery Selectors
jQuery selectors are one of the most important parts of the jQuery library.   
#### <a name="Methods">jQuery Event Methods   
Commonly Used jQuery Event Methods:  
  
##### $(document).ready()
The <span style="color: red;">`$(document).ready()`</span> method allows us to execute(执行) a function when the document is fully loaded. 
##### click()
The <span style="color: red;">`click()`</span> method attaches an event handler function to an HTML element.
```js
$("p").click(function(){
  $(this).hide();
});
```
###### dblclick()
The function is executed when the user double-clicks on the HTML element:
```js
$("p").dblclick(function(){
  $(this).hide();
});
```
##### mouseenter() / mouseleave()
The function is executed when the mouse pointer enters/leaves the HTML element:
```js
// mouseenter()
$("#p1").mouseenter(function(){
  alert("You entered p1!");
});

// mouseleave()
$("#p1").mouseleave(function(){
  alert("Bye! You now leave p1!");
});
```
##### mousedown() / mouseup()
The function is executed, when the left, middle or right mouse button is pressed down(按下)/released(松开), while the mouse is over the HTML element:  
  
```js
// mousedown()
$("#p1").mousedown(function(){
  alert("Mouse down over p1!");
});
// mouseup()
$("#p1").mouseup(function(){
  alert("Mouse up over p1!");
});
```
##### hover()
The <span style="color: red;">`hover()`</span> method takes two functions and is a combination of the <span style="color: red;">`mouseenter()`</span> and <span style="color: red;">`mouseleave()`</span> methods.
```js
$("#p1").hover(function(){
  alert("You entered p1!");
},
function(){
  alert("Bye! You now leave p1!");
});
```
##### focus() / blur()
The function is executed when the form field gets/loses focus:
```js
// focus()
$("input").focus(function(){
  $(this).css("background-color", "#cccccc");
});

// blur()
$("input").blur(function(){
  $(this).css("background-color", "#ffffff");
});
```
##### The on() Method
The on() method attaches one or more event handlers for the selected elements.  
  
Attach a click event to a <p> element:  
  
```js
// Attach a click event to a <p> element:
$("p").on("click", function(){
  $(this).hide();
}); 

// Attach multiple(多样的) event handlers to a <p> element:
$("p").on({
  mouseenter: function(){
    $(this).css("background-color", "lightgray");
  },
  mouseleave: function(){
    $(this).css("background-color", "lightblue");
  },
  click: function(){
    $(this).css("background-color", "yellow");
  }
}); 
```
### <a name="Effects">jQuery Effects
### <a name="index"/>Contents
- [jQuery Effects - Hide and Show](#EHS)  
- [jQuery Effects - Fading](#Fading)   
- [jQuery Effects - Sliding](#Sliding)  

#### <a name="EHS">jQuery Effects - Hide and Show
Hide, Show, Toggle(控制), Slide(滑动), Fade(逐渐消失), and Animate(动画). WOW!
##### jQuery hide() and show()
With jQuery, you can hide and show HTML elements with the <span style="color: red;">`hide()`</span> and <span style="color: red;">`show()`</span> methods:  
   
```js
$("#hide").click(function(){
  $("p").hide();
});

$("#show").click(function(){
  $("p").show();
}); 
```

`$(selector).hide(speed,callback);` speed parameter can take the following values: "slow", "fast", or milliseconds.  
  
`$(selector).show(speed,callback);` The optional callback parameter is a function to be executed after the `hide()` or `show()` method completes  
##### jQuery toggle()
You can also toggle between hiding and showing an element with the <span style="color: red;">`toggle()`</span> method.  
  
```js
$("button").click(function(){
  $("p").toggle();
}); $("button").click(function(){
  $("p").toggle();
}); 
```
  
`$(selector).toggle(speed,callback); `
#### <a name="Fading">jQuery Effects - Fading
##### jQuery Fading Methods
jQuery has the following fade(逐渐消失) methods:  
  
* <span style="color: red;">`fadeIn()`</span>  
* <span style="color: red;">`fadeOut()`</span>  
* <span style="color: red;">`fadeToggle()`</span>  
* <span style="color: red;">`fadeTo()`</span>  
  
##### jQuery fadeIn() / fadeOut() Method
The jQuery <span style="color: red;">`fadeIn()`</span> method is used to fade in(淡入) / fade out(淡出) a hidden element.  
  
```js
// $(selector).fadeIn(speed,callback);
// $(selector).fadeOut(speed,callback);

$("button").click(function(){
  $("#div1").fadeIn();
  $("#div2").fadeIn("slow");
  $("#div3").fadeIn(3000);
}); 

$("button").click(function(){
  $("#div1").fadeOut();
  $("#div2").fadeOut("slow");
  $("#div3").fadeOut(3000);
}); 
```

##### jQuery fadeToggle() Method
The jQuery <span style="color: red;">`fadeToggle()`</span> method toggles between the <span style="color: red;">`fadeIn()`</span> and <span style="color: red;">`fadeOut()`</span> methods.  
  
```js
// $(selector).fadeToggle(speed,callback);

$("button").click(function(){
  $("#div1").fadeToggle();
  $("#div2").fadeToggle("slow");
  $("#div3").fadeToggle(3000);
}); 
```

##### jQuery fadeTo() Method
The jQuery <span style="color: red;">`fadeTo()`</span> method allows fading to a given opacity(不透明性) (value between 0 and 1).  
  
```js
// $(selector).fadeTo(speed,opacity,callback);

$("button").click(function(){
  $("#div1").fadeTo("slow", 0.15);
  $("#div2").fadeTo("slow", 0.4);
  $("#div3").fadeTo("slow", 0.7);
}); 
```
    
####  <a name="Sliding">jQuery Effects - Sliding

### <a name="HTML">jQuery HTML
### <a name="Traversing">jQuery Traversing 
### <a name="AJAX">jQuery AJAX 
### <a name="Misc">jQuery MiscjQuery Effects - Sliding