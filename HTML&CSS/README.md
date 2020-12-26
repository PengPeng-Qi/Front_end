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
```<img src="image/drinks.gif" alt="The typical new pencil can draw a line 35 miles long." width="48" height="100">```   
    
* src属性不只是用于相对链接，还可以在src属性中放入URL。  
  
* alt属性需要指定描述这个图像的一些文本，如果图像未显示，就会使用这个文本来取代它。  
  
* width属性和height属性告诉浏览器在页面中显示图像的宽度与高度，宽度和高度都使用像素数指定。  
> * ```<img>```元素是一个void元素  
> * ```<img>```元素是一个内联元素，它不会在前面或后面插入换行。 
> * 一般，图像宽度小于800像素，logo宽度一般在100到200像素之间。  
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
#### style元素
```html
        <head>
            <title>Starbuzz Coffee</title>
            <style type="text/css">
            
            </style>
        </head>
```
> ```<style>```元素放在HTML的首部里，```<style>```标记还有一个（可选的）属性，名为type，它能告诉浏览器你在使用什么类型的样式。[例](./Sample/mission.html)
***
## 资料库 :triangular_flag_on_post:
### [Html颜色代码](http://www.shouce.ren/api/html/html4/appendix-color.html) 
> 用CSS指定颜色有很多不同的方式，最常用的一种方式为“十六进制码”，#d2b48c就是一个十六进制码，实际上是土黄色。
### [Html字体样式](https://www.w3schools.com/cssref/css_websafe_fonts.asp)  
### [w3schools_icons](https://www.w3schools.com/icons/default.asp)

