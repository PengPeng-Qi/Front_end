# 基础知识  :balloon:
## <a name="index"/>目录
* [HTML](#HTML)   
* [CSS](#CSS)
## <a name="HTML">超文本标记语言（HyperText Markup Language，HTML） :triangular_flag_on_post: 
超文本标记语言用来建立网页的结构。  

## <a name="index"/>目录
* [元素](#code)  
    * [结构](#structure)  
    * [链接](#connect)  
    * [引用文字](#he)  
    * [换行](#hh)  
    * [排序](#px)  
    * [图片](#im)  
    * [注释](#zs)  
* [其他元素](#other)    
* [嵌套](#qt)  
* [特殊字符](#spc)  
* [属性](#sx)  
* [HTML验证链接](#lj) 

### <a name="code"/>元素 :golf:
***
#### 元素 = 开始标记 + 内容 + 结束标记   
***
#### <a name="structure"/>结构  
***
**```<!doctype html>```元素**指定版本号：HTML5，放在开头   
  
**```<head>...</head>```元素**head元素的内容就是网页的信息  
    
**```<body>...</body>```元素**body元素的内容就是将在浏览器里看到的东西  
    
**```<meta>```标记**  
  
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
#### <a name="connect"/>链接   
***
**```<a>...</a>```元素**  
***
*  ```<a>```元素创建一个超文本链接，链接到另一个Web页面  

* ```<a>```元素的内容会成为Web页面中可单击的文本，在浏览器中，连接文本会显示有下划线，指示这是可单击  

* ```<a href="elixir.html">elixirs</a>```要通过href属性来指定链接的目标文件，对于这个链接，浏览器会显示文本”elixirs”，单击这个文本时，用户会被带往”elixir.html”页面。[例](./Sample/lounge.html)  
> 文字和图片都可以作为链接的标签
***
**href属性**  
***
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
#### <a name="he"/>引用文字  
***
**```<q>...</q>```内联元素**在HTML中**简短**的引用，在行内出现  
  
* ```<q>文本内容</q>```文本内容不用加双引号，但表示出来有双引号  
> 并不是所有的浏览器都会在```<q>```元素的内容两边加双引号，建议在浏览器上做一下测试
***

**```<blockquote>...</blockquote>```块元素**在HTML中**长**引用，自成一段  
> * ```<h1>```、```<h2>```、```<h6>```...```<p>```和```<blockquote>```都是块元素  
> * ```<q>```、```<a>```、```<em>```都是内联元素
***
#### <a name="hh"/>换行  
***
**```<br>```void元素**  

* ```<br>```元素是一个没有任何内容的元素，甚至没有结束标记，这类元素称为**void元素**  
    
* ```<br>```元素用来表示换行，没有任何内容，[例](./Sample/journal.html)
> * ```<img>```元素也是void元素  
> * ```<br/>```元素和```<br>```元素意思完全一样，处理XHTML时，```<br/>```元素更为严格，可以把它想象成是```<br>```元素
***
#### <a name="px"/>排序
***
**```<li>...</li>```、```<ol>...</ol>```、```<ul>...</ul>```元素**  

* 以上都是块元素，列表项需要移除段落，列表会独立显示，[例](./Sample/journal.html)    
  
* 创建一个列表，每个列表项要放入单独的```<li>...</li>```元素中  
    
* 使用```<ol>...</ol>```包围列表项，这些表项将作为一个**有序**列表显示  

* 使用```<ul>...</ul>```包围列表项，这些表项将作为一个**无序**列表显示  
> * **l**ist **i**tem -- **li**  
> * **o**rdered **l**ist -- **ol**  
> * **u**nordered **l**ist -- **ul**  
> * ```<ol>```与```<li>``` 或 ```<ul>```与```<li>``` 总是一起使用  
> * ```<ol>```和```<ul>```只能包含```<li>```元素  
> * 列表中镶嵌一个列表，可以把```<ol>```或```<ul>```作为某个```<li>```的内容，[例](./Sample/ul_ol_li.html)  
***
#### <a name="im"/>图片
***
**```<img>```元素**
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
#### <a name="zs"/>注释
***
把注释放在 ``` <!-- 和 --> ``` 之间，例如:  ```<!-- Here's the beginning of the lounge content --> ```   
> * 注释符号不能放在嵌套中  
> * 注意：```"<!--" 和 "-->"```之间放置的所有内容（甚至是HTML）都会被浏览器忽略。  
***
### <a name="other"/>其他元素 :golf:
***
* ```<code>```用来显示计算机程序的代码  
* ```<pre>```希望浏览器按输入的方式原样显示文本 
* ```<em>```使用这个元素来标记你想用不同方式展示的文本  
* ```<strong>```使用这个元素来标记你希望特别强调的文本  
* ```<time>```用来告诉浏览器这个内容是一个日期或时间，或者同时包含日期和时间   
### <a name="qt"/>嵌套 :golf:
***
把一个元素放在另一个元素里叫作嵌套  

* ```<q>```嵌套在```<p>```中  
* ```<p>```嵌套在```<body>```中  
* ```<body>```嵌套在```<html>```中  
* ```<title>```嵌套在```<head>```中  
* ```<head>```嵌套在```<html>```中  
### <a name="spc"/>特殊字符 :golf:
***
如果要在浏览器上显示"<"或">"等特殊符合，需要查找相应符号的字符实体，例如：  

* "<"字符实体为```&lt;```   
* ">"字符实体为```&gt;```  
* "&"字符实体为```&amp;```  
* 版权符号字符实体为```&copyright;```  
> 想要查询更多符号的字符实体，可进入[w3schools_icons](https://www.w3schools.com/icons/default.asp)查询
### <a name="sx"/>属性 :golf:
***
* ```html<a href="irule.html>```超文本引用（hypertextreference，href）属性告诉我们一个超链接的目标文件  

* ```<style type="text/css>```type属性告诉我们使用哪一种样式语言，这里是CSS  

* ```<img src="sweetphoto.gif"```src属性指定一个img标记显示的图像文件名  
> src为属性名，sweetphoto.gif为属性值
***
### <a name="lj"/>HTML验证链接[&#128279;](https://validator.w3.org/)
## <a name="CSS">层叠样式表（Cascading Style Sheets，CSS）  :triangular_flag_on_post:
层叠样式表用来控制HTML的表现。  
## <a name="index"/>目录
* [Style](#style)  
* [添加CSS](#ad)  
    - [Link元素](#link)  
    - [继承](#jicheng)  
    - [注释](#zhusi)  
    - [属性](#shuxing)  
    - [字体](#font)  
        - [字体大小](#fontsize)  
        - [字体颜色](#fontcolor)  
        - [字体粗细](#fontbold)  
        - [字体风格](#fontstyle)
        - [文本风格](#textstyle)  
* [类](#lei)  
* [CSS验证链接](#jianyan)  
* [资料库](#ziliao)  

### <a name="style"/>style元素 :golf:
```html
        <head>
            <title>Starbuzz Coffee</title>
            <style type="text/css">
            
            </style>
        </head>
```
> ```<style>```元素放在HTML的首部里，```<style>```标记还有一个（可选的）属性，名为type，它能告诉浏览器你在使用什么类型的样式。[例](./Sample/mission.html)  
***
### <a name="ad"/>添加CSS :golf:
增加CSS文件，若要改变```<p>```元素中内容的格式，则需要选择需要添加的元素，如：  
```css
p {
    background-color: red;
    border: 1px solid black;
}
/* 1px solid black设置下边框的样式：粗细为1像素，黑色，实线 */
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
#### <a name="link"/> ```<link>```元素  
```<link>```元素：从html到外部样式表,不再需要```<style>```元素    
```css
    <title>Head First Lounge</title>
    <link type="text/css" rel="stylesheet" href="lounge.css">
    /* lounge.css指链接到外部样式表的html */
```
* ```<link>```void元素，键入外部信息，放在```<head>```元素中    
* rel属性指定了HTML文件与所链接的文件之间的关系，我们要链接到一个样式表，所以这里使用值"stylesheet"   
***
#### <a name="jicheng"/>覆盖继承 
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
#### <a name="zhusi"/>注释
用```/*```和```*/```包围   
***
#### <a name="shuxing"/>属性
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
#### <a name="font"/>字体
***
##### 字体
```css
body {
    font-family: Verdana, Geneva, Arial, sans-serif;
}
/* 使用font-family属性可以指定多个字体，只需要输入这些字体名(大小写字母必须一致)，并用逗号隔离，最后放一个常用字体，例如sans-serif、monospace等 */
```
> 查看用户计算机是否有Verdana，如果有，则显示Verdana，如果没有Verdana，且有Geneva，则显示Geneva，依次进行，如果前面的字体都没有，则使用浏览器的默认字体"sans-serif"。   

每个font-family包含一组有共同特征的字体。共有五个字体系列：  

* sans-serif: 没有衬线的字体  
* serif: 有衬线的字体  
* monospace: 包含固定宽度的字体  
* cursive: 看似手写字体  
* fantasy: 某种风格的装饰字体   
> 若字体名为Courier New,则在两边加上引号，就像:```font-family:"Courier New", Courier;```  
> sans-serif并不是具体的字体名，他的字体的浏览器定义的字体的系列的默认字体  
***  
**Web字体**  
字体使用了一种".woff"的文件拓展名，这表示Web开放字体格式  
  
> * 字体常用格式：
> * TureType字体：            .tff  
> * OpenType字体：            .otf  
> * Embedded OpenType字体：   .eot  
> * SVG字体：                 .svg  
> * Web开放字体格式：          .woff  

**也可以把字体放在Web上：**  
```@font-face```: 获取一个Web字体，并为他分配一个font-family名   

```css
@font-face {
    font-family: "Emblema One";
    src: url("./EmblemaOne-Regular.woff"), 
         url("./EmblemaOne-Regular.ttf"); 
}
```
在CSS中使用font-family名
```css
h1 {
    font-family: "Emblema One", sans-serif;
}
```
> ```@import```: 允许导入其他CSS文件  
> ```@media```: 允许创建某些特定于某些“媒体”类型的CSS规则，如印刷页、手机

##### <a name="fontsize"/>字体大小
设置一个字体高度为14像素：字母的最低部分与最高部分之间的距离有14像素  
```css
body {
    font-size: 14px;
}
/* 字体大小font-size控制 */
```
> 默认body字体大小一般为16px  
> 标题默认大小:  
>   
> * ```<h1>```一般是默认字体的200%   
> * ```<h2>```一般是默认字体的150%  
> * ```<h3>```一般是默认字体的120%  
> * ```<h4>```一般是默认字体的100%  
> * ```<h5>```一般是默认字体的90%  
> * ```<h6>```一般是默认字体的60%  

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
关键字：  

> * xx-samll  
> * x-small  
> * samll    
> * medium  
> * large  
> * x-large  
> * xx-large  
  
> small在大多数浏览器中是12px，每个大小大约比前一个大20% 

**指定字体大小：**  

* 选择关键字，指定作为body规则中的字体大小，相当于页面的默认字体  
* 使用em或者百分数，相对于body字体大小指定其他元素的字体大小  
```css
body {
    font-size: small;
}
h1 {
    font-size: 150%;
}
h2 {
    font-size: 1.2em;
}
```  

**修改Web字体大小：**  
```css
@font-face {
    font-family: "Emblema One";
    src: url("./EmblemaOne-Regular.woff"), 
         url("./EmblemaOne-Regular.ttf"); 
}
body {
    font-family: Verdana, Geneva, Arial, sans-serif;
    font-size: small;
}
/* 在body中定义字体，相当于定义默认字体 */
h1 {
    font-family: "Emblema One", sans-serif;
    font-size: 220%;
}
h2 {
    font-size: 130%;
}
```
##### <a name="fontcolor"/>字体颜色
Web颜色是按构成颜色的红、绿、蓝三个分量所占数量来指定的  
> 红色100%、绿色100%、蓝色100%混合在一起，就会得到白色  
> 红色0%、绿色0%、蓝色0%混合在一起，就会得到黑色  

**按名字指定颜色**  
```css
body {
    color: silver;
}
```
**用红、绿、蓝值指定颜色**  
```css
body {
    background-color: rgb(80%, 40%, 0%);
}
```
```css
body {
    background-color: rgb(204, 102, 0);
}
```
**使用十六进制码指定颜色**  
一个十六进制码中，每组2位数字分别代表颜色的红、绿、蓝分量,就像```#cc6600```,```#cc6600```可以缩写成```#c60```    
##### <a name="fontbold"/>字体粗细
```css
body {
    font-weight: bold;
}
/* 粗体 */
```
```css
body {
    font-weight: normal;
}
```
##### <a name="fontstyle"/>字体风格
```font-style```属性为文本增加风格  

> 不是所有的字体都支持斜体风格(italic),所以你得到的实际上是倾斜文本(oblique)  
##### <a name="textstyle"/>文本风格
```css
body {
    text-decoration: underline;
}
/* underline下划线*/
```
```css
em {
    text-decoration: line-through;
}
/* linethrough 表示em元素上有一个从文本中间穿过的横线*/
```
```css
em {
    text-decoration: underline overline;
}
/* underline overline使得em元素有一个下划线和一个上划线 */
```
```css
em {
    text-decoration: none;
}
/* none 表示em元素没有任何装饰 */
```

***
#### <a name="lei"/>增加类
```html
    <p class="greentea">
    <!-- 要将一个元素加入一个类，只需要增加元素"class",并提供类名"greentea" -->
```
```css
    p.greentea {
        color: green;
    }
    /* p.greentea类选择器 */
```
若想再对```<blockquote>```也做同样的处理  
```css
blockquote.greentea, p.greentea {
    color: green;
}
```
在html中也需要写上  
```html
<blockquote class="greentea">
```
如果想把```<h1>```、```<h2>```、```<p>```、```<blockquote>```都增加到greentea类，可以在css中写入
```css
.greentea {
    color: green;
}
```
> 如果省略元素名，只有一个点，后面是类名，那么这个规则会应用到这个类的所有成员
##### 一个元素加入多个类
```html
<p class="greentea raspberry blueberry">
<!-- 类名的顺序不重要,会按照CSS文件最后一个值来选择 -->
```
## <a name="jianyan"/>CSS验证链接[&#128279;](http://jigsaw.w3.org/css-validator/)
## <a name="ziliao"/>资料库 :triangular_flag_on_post:
### [Html颜色代码](https://en.wikipedia.org/wiki/Web_colors#HTML_color_names) 
> 用CSS指定颜色有很多不同的方式，最常用的一种方式为“十六进制码”，#d2b48c就是一个十六进制码，实际上是土黄色。
### [Html字体样式](https://www.w3schools.com/cssref/css_websafe_fonts.asp)  
### [w3schools_icons](https://www.w3schools.com/icons/default.asp) 
### 字体托管网站:[FontSquiriel](https://www.fontsquirrel.com/)、[Google Web字体服务](https://fonts.google.com/)  
