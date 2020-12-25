# 基础知识
## 超文本标记语言（HyperText Markup Language，HTML）  
超文本标记语言用来建立网页的结构。  
#### 元素 = 开始标记 + 内容 + 结束标记  
#### 注释：
把注释放在 ``` <!-- 和 --> ``` 之间，例如``` <!-- Here's the beginning of the lounge content --> ```   
> 注意：```"<!--" 和 "-->"```之间放置的所有内容（甚至是HTML）都会被浏览器忽略。
#### head元素：
head元素的内容就是网页的信息
#### body元素：
body元素的内容就是将在浏览器里看到的东西
#### ```<a>...</a>```元素
```<a>```元素用于创建指向另一个页面的链接  
```<a>```元素的内容就是连接文本。在浏览器中，连接文本会显示有下划线，指示这是可单击的  
```<a href="elixir.html">elixirs</a>```要通过href属性来指定链接的目标文件，对于这个链接，浏览器会显示文本”elixirs”，单击这个文本时，用户会被带往”elixir.html”页面。[例](./lounge.html)
## 层叠样式表（Cascading Style Sheets，CSS）  
层叠样式表用来控制HTML的表现。  
#### style元素：
```<html>
        <head>
            <title>Starbuzz Coffee</title>
            <style type="text/css">
            
            </style>
        </head>
```
> ```<style>```元素放在HTML的首部里，```<style>```标记还有一个（可选的）属性，名为type，它能告诉浏览器你在使用什么类型的样式。[例](./mission.html)
## 资料库
### [Html颜色代码](http://www.shouce.ren/api/html/html4/appendix-color.html) 
> 用CSS指定颜色有很多不同的方式，最常用的一种方式为“十六进制码”，#d2b48c就是一个十六进制码，实际上是土黄色。
### [Html字体样式](https://www.w3schools.com/cssref/css_websafe_fonts.asp)  

