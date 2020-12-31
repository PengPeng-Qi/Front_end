# 基础知识  :balloon:
## 超文本标记语言（HyperText Markup Language，HTML） :triangular_flag_on_post: 
超文本标记语言用来建立网页的结构。  
### 元素 :golf:
#### 元素 = 开始标记 + 内容 + 结束标记   
***
#### 注释
把注释放在 ``` <!-- 和 --> ``` 之间，例如:  ```<!-- Here's the beginning of the lounge content --> ```   
> 注意：```"<!--" 和 "-->"```之间放置的所有内容（甚至是HTML）都会被浏览器忽略。
***
#### ```<!doctype html>```
指定版本号：HTML5，放在开头。   
***
#### ```<head>...</head>```元素
head元素的内容就是网页的信息
***
#### ```<body>...</body>```元素
body元素的内容就是将在浏览器里看到的东西
***
#### ```<a>...</a>```元素
```<a>```元素创建一个超文本链接，链接到另一个Web页面  

```<a>```元素的内容会成为Web页面中可单击的文本，在浏览器中，连接文本会显示有下划线，指示这是可单击  

```<a href="elixir.html">elixirs</a>```要通过href属性来指定链接的目标文件，对于这个链接，浏览器会显示文本”elixirs”，单击这个文本时，用户会被带往”elixir.html”页面。[例](./Sample/lounge.html)  
> 文字和图片都可以作为链接的标签
***
#### ```<q>...</q>```内联元素
在HTML中简短的引用，在行内出现  
```<q>文本内容</q>```文本内容不用加双引号，但表示出来有双引号  
> 并不是所有的浏览器都会在```<q>```元素的内容两边加双引号，建议在浏览器上做一下测试
***
#### ```<blockquote>...</blockquote>```块元素
在HTML中长引用，自成一段  
> * ```<h1>```、```<h2>```、```<h6>```...```<p>```和```<blockquote>```都是块元素  
> * ```<q>```、```<a>```、```<em>```都是内联元素
***
#### ```<br>```void元素
```<br>```元素是一个没有任何内容的元素，甚至没有结束标记，这类元素称为**void元素**  
    
```<br>```元素用来表示换行，没有任何内容，[例](./Sample/journal.html)
> * ```<img>```元素也是void元素  
> * ```<br/>```元素和```<br>```元素意思完全一样，处理XHTML时，```<br/>```元素更为严格，可以把它想象成是```<br>```元素
***
#### ```<li>...</li>```、```<ol>...</ol>```、```<ul>...</ul>```元素
以上都是块元素，列表项需要移除段落，列表会独立显示，[例](./Sample/journal.html)    
  
创建一个列表，每个列表项要放入单独的```<li>...</li>```元素中  
    
使用```<ol>...</ol>```包围列表项，这些表项将作为一个**有序**列表显示  

使用```<ul>...</ul>```包围列表项，这些表项将作为一个**无序**列表显示  
> * **l**ist **i**tem -- **li**  
> * **o**rdered **l**ist -- **ol**  
> * **u**nordered **l**ist -- **ul**  
> * ```<ol>```与```<li>``` 或 ```<ul>```与```<li>``` 总是一起使用  
> * ```<ol>```和```<ul>```只能包含```<li>```元素  
> * 列表中镶嵌一个列表，可以把```<ol>```或```<ul>```作为某个```<li>```的内容，[例](./Sample/ul_ol_li.html)  
***
#### ```<img>```元素
```html
    <img src="image/drinks.gif" alt="The typical new pencil can draw a line 35 miles long." width="48" height="100">
```   
* src属性不只是用于相对链接，还可以在src属性中放入URL。  
  
* alt属性需要指定描述这个图像的一些文本，如果图像未显示，就会使用这个文本来取代它。  
  
* width属性和height属性告诉浏览器在页面中显示图像的宽度与高度，宽度和高度都使用像素数指定。  
> * ```<img>```元素是一个void元素  
> * ```<img>```元素是一个内联元素，它不会在前面或后面插入换行。 
> * 一般，图像宽度小于800像素，logo宽度一般在100到200像素之间。  
***
#### ```<meta>```标记
```html
<meta charset="utf-8">
```  
* charset -- 要在charset属性中指定字符编码   

* meta -- 表示我们要告诉浏览器关于页面的一些信息...   

* utf--8 -- 是[unicode](https://zh.wikipedia.org/wiki/Unicode)系列中的一个编码，Web页面中使用的就是utf-8，详情见[&#128279;](https://www.w3schools.com/charsets/)  
> * ```<meta>```标记要放在```<head>```元素中，放在元素```<title>```上  
> * ```<head>```元素中放置```<title>```、```<meta>```、```<style>```元素  
> * void元素中不能嵌套内联元素,例如```<img>```，在```<img>```元素中，src、alt属性是必要的      
***
#### 其他元素
* ```<code>```用来显示计算机程序的代码  
* ```<pre>```希望浏览器按输入的方式原样显示文本 
* ```<em>```使用这个元素来标记你想用不同方式展示的文本  
* ```<strong>```使用这个元素来标记你希望特别强调的文本  
* ```<time>```用来告诉浏览器这个内容是一个日期或时间，或者同时包含日期和时间   
### 嵌套 :golf:
把一个元素放在另一个元素里叫作嵌套  
* ```<q>```嵌套在```<p>```中  
* ```<p>```嵌套在```<body>```中  
* ```<body>```嵌套在```<html>```中  
* ```<title>```嵌套在```<head>```中  
* ```<head>```嵌套在```<html>```中  
### 特殊字符 :golf:
    如果要在浏览器上显示"<"或">"等特殊符合，需要查找相应符号的字符实体，例如：  
* "<"字符实体为```&lt;```   
* ">"字符实体为```&gt;```  
* "&"字符实体为```&amp;```  
* 版权符号字符实体为```&copyright;```  
> 想要查询更多符号的字符实体，可进入[w3schools_icons](https://www.w3schools.com/icons/default.asp)查询
### 属性 :golf:
```<a href="irule.html>```超文本引用（hypertextreference，href）属性告诉我们一个超链接的目标文件  

```<style type="text/css>```type属性告诉我们使用哪一种样式语言，这里是CSS  

```<img src="sweetphoto.gif"```src属性指定一个img标记显示的图像文件名  
> src为属性名，sweetphoto.gif为属性值
***
#### href属性
> 若文件夹lounge中有lounge.html文件 + 文件夹about，文件夹about中有directions.html
##### 向下链接到一个子文件夹
lounge.html中的```<a>```元素是这样的：  
```html
    <a href="about/directions.html"> directions</a>
```
##### 向上链接到一个父文件夹
diretions.html中的```<a>```元素是这样的：  
```html  
    <a href="../lounge.html">Back to the Lounge</a>
``` 
如果需要向上两级文件夹，则使用:  
```html  
    <a href="../../lounge.html">Back to the Lounge</a>
``` 
> * src元素也一样  
> * 为网站选择的文件名和文件夹名中不能使用空格
***
## 层叠样式表（Cascading Style Sheets，CSS）  :triangular_flag_on_post:
层叠样式表用来控制HTML的表现。  
### style元素 :golf:
```html
        <head>
            <title>Starbuzz Coffee</title>
            <style type="text/css">
            
            </style>
        </head>
```
> ```<style>```元素放在HTML的首部里，```<style>```标记还有一个（可选的）属性，名为type，它能告诉浏览器你在使用什么类型的样式。[例](./Sample/mission.html)  
***
### 添加CSS :golf:
若要改变```<p>```元素中内容的格式，则需要选择需要添加的元素，如：  
```css
p {
    background-color: red;
    border: 1px solid gray;
}
```
> * CSS的规则需要放在```<style>```元素中  
  
改变标题的字体和颜色：  
```css
    h1 {
        font-family: sans-serif;
        color: gray;
        border-bottom: 1px solid gray;
    }   
    h2 {
        font-family: sans-serif;
        color: gray;
        border-bottom: 1px solid gray;
    }
```
也可以写成：  
```css
    h1, h2 {
        font-family: sans-serif;
        color: gray;
        border-bottom: 1px solid gray;
    }    
```
> * 上面的"h1","h1,h2"叫作**选择器**(selector)  
> * border-bottom这个属性控制元素下边框的外观  
> * sans-serif字体适合作标题，这种字体没有衬线，段落一般使用serif字体，有[衬线](https://baike.baidu.com/item/%E8%A1%AC%E7%BA%BF%E5%AD%97%E4%BD%93)  
> * 使用border-bottom，这条线会延伸到页面边缘，而使用underline时，下划线只会出现在文本下面  
***
#### ```<link>```元素  
不再需要```<style>```元素  
```css
    <link type="text/css" rel="stylesheet" href="lounge.css">
```
* ```<link>```void元素，键入外部信息，放在```<head>```元素中    
* rel属性指定了HTML文件与所链接的文件之间的关系，我们要链接到一个样式表，所以这里使用值"stylesheet"  
***
#### 覆盖继承 
若想在```<body>```中使用字体sans-serif,又想在```<em>```中使用字体serif，则  
```css
body {
    font-family: sans-serif;
}

em {
    font-family: serif;
}
```
> ```<em>```元素嵌套在```<body>```内，更多继承规则见《CSS Pocket Reference》   
***
#### 注释
用```/*```和```*/```包围   
***
#### 属性
* color: 设置文本元素字体颜色  
* background-color: 控制元素的背景颜色  
* background-image: 在元素后面放置一张图像  
* top: 控制元素顶部的位置  
* left: 指定一个元素的左边所在位置  
* list-style: 允许改变列表中列表项的外观  
* border: 在一个元素周围加边框。可以有一个实线边框、凸起边框、虚线边框...  
* padding: 如果在一个元素边缘和它的内容之间需要有空间，可以使用padding(内边距)  
* letter-spacing: 在字母之间设置间距  
* font-style: 设置斜体文本  
* font-size: 让文本更大或者更小  
* font-weight: 控制文本的粗细，可以用它设置粗体  
* text-align: 将文本左对齐，居中或者右对齐  
* text-decoration: 对文本加一些装饰，包括上划线、下划线和删除线  
***
#### font-family字体体系
* sans-serif: 没有衬线的字体  
* serif: 有衬线的字体  
* monospace: 包含固定宽度的字符  
* cursive: 看似手写的字体  
* fantasy: 包含某种风格的装饰性字体  
#### 特殊CSS规则
* ```@font-face```: 获取一个Web字体，并为他分配一个font-family名  
```css
@font-face {
    font-family: "Emblema One";
    src: url("./EmblemaOne-Regular.woff"), 
         url("./EmblemaOne-Regular.ttf"); 
}
```
* ```@import```: 允许导入其他CSS文件  
* ```@media```: 允许创建某些特定于某些“媒体”类型的CSS规则，如印刷页、手机  
***
#### 字体大小
设置一个字体高度为14像素：字母的最低部分与最高部分之间的距离有14像素  
```css
body{
    font-size: 14px;
}
```
父元素的1.5倍：  
```css
h1 {
    font-size: 150%;
}
```
等同于：
```css
h1 {
    font-size: 1.5em;
}
```
## HTML验证链接[&#128279;](https://validator.w3.org/)
## CSS验证链接[&#128279;](http://jigsaw.w3.org/css-validator/)
## 资料库 :triangular_flag_on_post:
### [Html颜色代码](http://www.shouce.ren/api/html/html4/appendix-color.html) 
> 用CSS指定颜色有很多不同的方式，最常用的一种方式为“十六进制码”，#d2b48c就是一个十六进制码，实际上是土黄色。
### [Html字体样式](https://www.w3schools.com/cssref/css_websafe_fonts.asp)  
### [w3schools_icons](https://www.w3schools.com/icons/default.asp)
### 字体托管网站:[FontSquiriel](https://www.fontsquirrel.com/)、[Google Web字体服务](https://fonts.google.com/)  

