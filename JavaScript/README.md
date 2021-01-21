## <a name="link"/>JavaScript目录:triangular_flag_on_post:
* [语法和基本构造](#yufa)  
* [学些DOM操作](#DOM)  
* [学习Fetch API / Ajax(XHR)](#FAA)  
* [ES6+ 和模块化 JavaScript](#EJ)  
* [学习一些概念：](#GN)  
    * 变量提升  
    * 事件冒泡  
    * 作用域  
    * 原型  
    * Shadow DOM  
    * 严格模式  
***
### <a name="yufa"/>语法和基本构造 :golf:
#### <a name="link"/>目录
* [运算符号](#FH)  
* [数据类型](#DateTypes)
***
##### <a name="FH">运算符号
除```/```:
```js
<!DOCTYPE html>
    <html>
        <body>

            <h2>The / Operator</h2>

            <p id="demo"></p>

            <script>
                var x = 5;
                var y = 2;
                var z = x / y;
                document.getElementById("demo").innerHTML = z;
            </script>

        </body>
    </html>
```
```
The / Operator
  
2.5
```
余```%``` :  
```js
<script>
    var x = 5;
    var y = 2;
    var z = x % y;
</script>
```
```txt
The % Operator
  
1
```
增量式```++```：  
```js
<!DOCTYPE html>
    <html>
        <body>

            <h2>The ++ Operator</h2>

            <p id="demo"></p>

            <script>
                var x = 5;
                x++;
                var z = x / y;
                document.getElementById("demo").innerHTML = z;
            </script>

        </body>
    </html>
```
```txt
The ++ Operator

6
```
> 同理：```--```递减
   
求幂：  
  
* ```**```  
* ```Math.pow(x,y)```  
  
```js
<script>
    var x = 5;
    document.getElementById("demo").innerHTML = Math.pow(x,2);
</script>
```
运算符号优先级表[&#128279;](https://www.w3school.com.cn/js/js_arithmetic.asp)  
***
##### <a name="DateTypes">数据类型
当添加数字和字符串时，JavaScript会将数字视为字符串  
```js
var x = 16 + "Volvo";
//等同于
var x = "16" + "Volvo";
```
JavaScript从左到右评估表达式。不同的序列可以产生不同的结果：  

```js
var x = 16 + 4 + "Volvo";
//20Volvo
```
```js
var x = "Volvo" + 16 + 4;
//Volvo164
```
JavaScript具有**动态类型**。这意味着可以使用同一变量来保存不同的数据类型：  
```js
var x;           // Now x is undefined
x = 5;           // Now x is a Number
x = "John";      // Now x is a String
```
###### 字符串 :round_pushpin:
**字符串**用引号引起来。您可以使用单引号或双引号：  
```js
var carName1 = "Volvo XC60";   // Using double quotes
var carName2 = 'Volvo XC60';   // Using single quotes
```
###### 数字 :round_pushpin:
**数字**可以带或不带小数：  
```js
var x1 = 34.00;     // Written with decimals
var x2 = 34;        // Written without decimals
```
可以使用科学（指数）表示法来写特大号或小号：
```js
var y = 123e5;      // 12300000
var z = 123e-5;     // 0.00123
```
###### 布尔值 :round_pushpin:
**布尔值**只能有两个值：true或false  
```js
var x = 5;
var y = 5;
var z = 6;
(x == y)       // Returns true
(x == z)       // Returns false
```
> 在条件测试中经常使用布尔值  
  
###### 数组 :round_pushpin:
JavaScript数组用方括号括起来,数组项用逗号分隔  
```js
var cars = ["Saab", "Volvo", "BMW"];
```
###### 对象 :round_pushpin:
JavaScript对象用大括号编写```{}```,对象属性写为名称：值对，用逗号分隔  
```js
var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
```
###### 运算符的类型 :round_pushpin:
使用JavaScript ```typeof```运算符来查找JavaScript变量的类型  
```js
typeof ""             // Returns "string"
typeof "John"         // Returns "string"
typeof 3.14           // Returns "number"
typeof (3)            // Returns "number"
```
###### 未定义 :round_pushpin:  
在JavaScript中，没有值的变量具有value undefined。类型也是undefined  
```js
var car;    // Value is undefined, type is undefined
```
>通过将值设置为，可以清空任何变量undefined。类型也将是undefined  
> ```js
> car = undefined;    // Value is undefined, type is undefined
> ```