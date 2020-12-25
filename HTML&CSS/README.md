# 基础知识
## 超文本标记语言（HyperText Markup Language，HTML）  
超文本标记语言用来建立网页的结构。  
### 元素
#### 元素 = 开始标记 + 内容 + 结束标记  
#### 注释
把注释放在 ``` <!-- 和 --> ``` 之间，例如:  
```html
     <!-- Here's the beginning of the lounge content --> 
```   
> 注意：```"<!--" 和 "-->"```之间放置的所有内容（甚至是HTML）都会被浏览器忽略。
#### head元素
head元素的内容就是网页的信息
#### body元素
body元素的内容就是将在浏览器里看到的东西
#### ```<a>...</a>```元素
```<a>```元素创建一个超文本链接，链接到另一个Web页面  

```<a>```元素的内容会成为Web页面中可单击的文本，在浏览器中，连接文本会显示有下划线，指示这是可单击  

```<a href="elixir.html">elixirs</a>```要通过href属性来指定链接的目标文件，对于这个链接，浏览器会显示文本”elixirs”，单击这个文本时，用户会被带往”elixir.html”页面。[例](./Sample/lounge.html)
### 属性
```<a href="irule.html>```超文本引用（hypertextreference，href）属性告诉我们一个超链接的目标文件  

```<style type="text/css>```type属性告诉我们使用哪一种样式语言，这里是CSS  

```<img src="sweetphoto.gif"```src属性指定一个img标记显示的图像文件名  
> src为属性名，sweetphoto.gif为属性值
#### href属性
> 若文件夹lounge中有lounge.html文件 + 文件夹about，文件夹about中有directions.html
##### 向下链接到一个子文件夹
lounge.html中的```<a>```元素是这样的：  
```html
    <a href="about/directions.html"> directions</a>
```
##### 向上链接到一个父文件夹
diretions.html中的```<a>```元素是这样的：```<a href="../lounge.html">Back to the Lounge</a>``` 
> 如果需要向上两级文件夹，则使用```<a href="../../lounge.html">Back to the Lounge</a>``` 
## 层叠样式表（Cascading Style Sheets，CSS）  
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
## 资料库
### [Html颜色代码](http://www.shouce.ren/api/html/html4/appendix-color.html) 
> 用CSS指定颜色有很多不同的方式，最常用的一种方式为“十六进制码”，#d2b48c就是一个十六进制码，实际上是土黄色。
### [Html字体样式](https://www.w3schools.com/cssref/css_websafe_fonts.asp)  

