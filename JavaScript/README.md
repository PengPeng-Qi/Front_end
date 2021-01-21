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