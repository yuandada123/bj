# **js基础笔记**

## **变量与数据**

|类型名称 |值|说明|
|---------|------|----------------|
|数值     |100;3.14  |不管是整数还是小数，都是数值型。|
|字符串   |"hello";"100"  |双引号或单引号中的值是字符串。|
|布尔     |true;false  |布尔值只有两个值，代表真和假。|
|空       |null|空值只有null，后续讲解。|
|未定义   |undefined  |未定义值只有undefined，后续讲解|
|对象     |{}  |后续讲解|

## **表达式与运算符**
|运算符|操作|类型|
|------|----|--------|
|+|加|num,num=>num|
|-|减|num,num=>num|
|*|乘|num,num=>num|
|/|除|num,num=>num|
|%|求余|num,num=>num|
|++|自增1|num=>num|
|--|自减1|num=>num|

|运算符|操作|类型|
|------|----|--------|
|>|大于|num,num=>bool|
|>=|大于等于|num,num=>bool|
|<|小于|num,num=>bool|
|<=|小于等于|num,num=>bool|
|==|判断相等|any,any=>bool|
|!=|判断不等|any,any=>bool|
|===|判断恒等|any,any=>bool|
|!==|判断非恒等|any,any=>bool|

|运算符|操作|类型|
|------|----|--------|
|&&|逻辑与|any,any=>any|
||||逻辑或|any,any=>any|
|!|逻辑非|bool,bool|

|运算符|操作|类型|
|------|----|--------|
|=|赋值|any,any=>any|
|+=|加并赋值|any,any=>any|
|-=|减并赋值|any,any=>any|
|*=|乘并赋值|any,any=>any|
|/=|除并赋值|any,any=>any|

## **条件循环**
  if和else是判断语句 放结果是true的时候会执行if里面的内容，当结果为false的时候会执行else里面的内容。
####**if和else案例**
```js
var num1 = 10;
var num2 = 20;
if(num1<num2){
    console.log("num1小于num2");
}else{
    console.log("num1大于num2");
}
// 上面会输出num1小于你num2;

```
### **通过修改操作符，输出不同的结果**

```js
var num1 = 10;
var num2 = 20;
var sign = "+";
var result =  0; //储蓄结果
if(sign ==="+"){
    result = num1 + num2;
    console.log(result);
}else if(sign === "-"){
    result = num1 - num2;
    console.log(result)
}else if(sign === "*"){
    result = num1 * num2;
    console.log(result)
}else if(sign === "/"){
    result = num1 / num2;
    console.log(result)
}else{
    console.log("请输入正确的操作符")
}
```

### **上面的内容可以通过switch来简化**

```js

var num = 0;
switch(num){
    case "+":return n+m;break;
    case "-":return n-m;break;
    case "*":return n*m;break;
    case "/":return n/m;break;
    default:console.log("请输入正确的操作符");break;
}
```
#### **表达式**
```js
表达式?第一个值：第二个值
```

如果表达式为true，表达式的返回值会是第一个值，如果表达为false，那么表达式的返回值是第二个值代码如下

```js
var num1 = 10;
var num2 = 20;
var result = num1 > num2 ? 100 : 200;
console.log(result);
```

## 循环语句

在for语句中，如果布尔值是true,就会一直执行语句块中的内容，为了防止死循环，需要有一个计数器，当数值达到指定值，布尔值就会变成false，循环便停止了，下面的示例代码使用for循环输出0~9九个数字
```js
for(var i = 0;i<10;i++){  
    // i的初始值是0
    // 判断i是否小于10，如果小于10则执行花括号中的代码
    // 每次执行完花括号中的代码后，i的值加1
    console.log(i);
}
```

通过上面的例子我们进一步理解了for语句的用法，下面我们来做一个联系，利用for循环语句输出100以内所有正整数的加

``` js
var sum = 0;                 //sum用来存储循环过程中正整数的加和
for(var i = 1;i<=100;i++){
    sum += i;
}
console.log(sum);
```

### while语句

```js
var n = 0;
while(n<10){
    console.log(n);
    n++;
}
```
### conthinue
continue可以结束本次循环，直接进入到下一次循环，例如我们用for循环语句来实现输出0~5,7~9九个数字（跳过6）
``` js
var sum = 0;
for(var i = 0;i<=100;i++){
    if(i%7===0){
        continue;
    }
    sum += i;
}
console.log(sum);
```
#### 五、break
在学switch语句中，我们已经解除到了break，它可以让分支语句在结束一个case之后，跳出switch语句，break同样可以用在循环语句当中，当代码执行到break时，直接结束循环（demo07.html）
``` js
for(var i = 0;i<10;i++){
    if(i===6){
        break;
    }
    console.log(i);
}
```

## 函数基础
   ### 函数的应用案例
函数是一个可执行的语句块，定义的时候不执行，调用的时候执行，使用"函数名()"的形式可以调用函数，可以重复调用
``` js
function count(num1,sign,num2){
    var result = 0;
    switch(sign){
        case "+":result = num1 + num2;break;
        case "-":result = num1 - num2;break;
        case "*":result = num1 * num2;break;
        case "/":result = num1 / num2;break;
        default:console.log("请输入正确的操作符")
    }
    return result;
}
console.log(count(10,"*",20));
```

## 对象

#### 三、方法


#### 二、自定义对象
我们可以通过一对花括号来创建一个对象
``` js
var obj = {};
```
#### 三、方法
通过上面的例子我们可以知道name的属性值是字符串类型，age的属性值是数值类型。其实对象的属性值可以是任何数据类型，甚至可以是函数，如果对象的属性值是函数，那么我们叫这个属性为这个对象的方法（demo02.html）。

``` js
var cat = {
    name:"喵喵",
    age:2,
    sayName:function(){
        console.log("我是喵喵");
    }
}
cat.sayName();
```

在花括号中，我们可以为对象定义属性，下面我们来写一个猫的对
``` js
var cat = {               //定义一个对象cat,它有两个属性，name和age
    name:"喵喵",
    age:2
}
//有两种方法可以获取到对象的属性值：1、对象名.属性名；2、对象名["属性名"]
console.log(cat.name);    
console.log(cat["name"]);
```

在对象的方法中使用this，可以指向这个对象本身，代码如下
``` js
var cat = {
    name:"喵喵",
    age:2,
    sayName:function(){
        console.log("我是"+this.name)
    }
}
cat.sayName();            
cat.name = "小白";
console.log(cat.name);   
cat.sayName();           
```
#  数组
###创建数组

```js

var i = [0,1,2,3,4,5,6,7,8,9]
```

###在数组中添加元素
* push给数组追加元素
```js
var friends = ["小明","小亮"];
friends.push("小红");
console.log(friends);
```
### 读取数组长度
* length读取数组长度
```js
var numlist = [1,3,5,7,9];
console.log(numlist.length)
```

* **Number只能输入数字**

#DOM基础
我们可以通过DOM提供的querySelector方法来获取元素，然后进一步操作它的样式
```html
<h1>DOM样式测试</h1>
<script>
    var h1 = document.querySelector("h1");  
    //querySelector的返回值是一个DOM对象，该方法可以通过选择器获取元素，若选择器找到多个元素，则返回第一个。
    h1.style.color = "red"; 
    //DOM对象的style属性可以设置元素内联样式。
</script>
```
若需要通过js设置多个元素的样式，可以使用querySelectorAll方法，代码如下

``` html
<ul>
    <li>香蕉</li>
    <li>苹果</li>
    <li>鸭梨</li>
</ul>
<script>
    var ali = document.querySelectorAll("li");
    //querySelectorAll方法的返回值是一个类数组的集合，里面保存的是获取的所有元素，所以如果希望为每一个元素设置样式，需要遍历这个集合。
    for(var i = 0;i<ali.length;i++){
        ali[i].style.color = "red";
    }
</script>
```

#### 三、绑定事件
事件就是文档或者浏览器窗口发生的一些特定的交互瞬间，例如：用户点击网页会触发点击事件（click），用户在元素上移动会触发鼠标移动事件（mousemove）等。下面我们来定义一个点击事件，当我们点击一个按钮的时候，弹出"hello world"（demo03.html）
``` html
<button>按钮</button>
<script>
    var btn = document.querySelector("btn");
    btn.onclick = function(){
        console.log("hello world");
    }
</script>
```


* 我们可以通过JavaScript获取和设置元素属性，例如input的value属性值，或者img的src属性。

* createTextNode创建元素
* appendChild添加元素
* removeChild删除元素
* parentNode找父级

#事件流

我们还可以用使用事件监听器为元素绑定事件，代码如下,不会覆盖之前的内容
``` js
btn.addEventListener("click",function(){});
```

## 计时器方法

### 一、计时器方法概述
计时器方法可以实现在指定的时间过后，单词或重复调用函数的功能，setTimeout可以实现函数在指定毫秒数后单词执行，setInterval可以实现函数在指定毫秒数后重复执行，语法如下所示：
``` js
setTimeout(function(){
    //一秒后执行
},1000);

setInterval(function(){
    //一秒后执行，并且每隔一秒重复执行
},1000)
```

当计时器开始计时后，我们可以使用clearTimeout方法让计时器停下来，下面我们来定义一个按钮，当页面加载后，如果我们在3秒钟之内点击按钮，计时器会停止，不会输出hello world，如果不点击按钮，3秒钟之后就会输出hello world。

``` js
var btn = document.querySelector("button");
var t = setTimeout(function(){
    console.log("hello world");
},3000)
btn.onclick = function(){
    clearTimeout(t);
}
```

# 内置对象

### 二、Math
Math对象不像数组那样需要我们手动去创建，我们在JavaScript程序中直接写Math代表的就是Math对象。我们可以通过Math对象直接获取圆周率。
``` js
var pi = Math.PI;
console.log(pi);
```
``` js
var pi = Math.PI;   
var num1 = Math.floor(pi);  //向下取整
var num2 = Math.ceil(pi);   //向上取整
var num3 = Math.round(pi);  //四舍五入
var num4 = Math.abs(-pi);   //获取绝对值
var num5 = Math.random();   //获取0~1之间的随机数
```
## 随机数
``` js
var number = Math.floor(Math.random()*10 + 1);
console.log(number);
```
## Date
Date对象是JavaScript用于处理日期和时间的对象，我们可以通过Date对象获取当前的时间，需要说明的是Date对象获取的时间是本机的时间。
``` js
var dateNow = new Date();
var year = dateNow.getFullYear();    //获取年，不能用getYear()方法，此方法已经被废弃
var month = dateNow.getMonth();      //获取月份 从0开始，一月份返回的值是0
var date = dateNow.getDate();        //获取日期
var hours = dateNow.getHours();      //获取小时
var minutes = dateNow.getMinutes();  //获取分钟
var seconds = dateNow.getSeconds();  //获取秒
var day = dateNow.getDay();          //获取星期

getTime //计算毫秒
```

# 正则表达式
``` js
var arr = new Array();   //创建数组
var reg = new RegExp();  //创建正则表达式
```
* 简单写法
``` js
var arr = [1,2,3];   //创建数组
var reg = /123/;     //创建正则表达式
```
* test判断平等
* exec判断包括文字

``` js
var reg = /^123$/;  //^表示开头，$表示结尾，两个符号之间是匹配的内容
var str = "012345";
console.log(reg.exec(str));
```
``` js
var reg = /[123]/;  //匹配123中的任意一个字符
var str = "02468";  
console.log(reg.exec(str));
```

``` js
var reg = /[0-9]/;  //匹配一位数字
var str = "02468";  
console.log(reg.exec(str));
```
``` js
var reg = /[a-z]+/;  //匹配多位字母
var str = "012345abcde";  
console.log(reg.exec(str));
```

``` js
var reg = /[a-z]{3}/;  //匹配3位字母
var str = "012345abcde";  
console.log(reg.exec(str));
```