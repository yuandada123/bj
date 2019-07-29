# jQuery基础 

#### 第一章：属性样式

**更改css的样式**


``` html
<body>
	<h1>hello jquery</h1>
	<script src="script/jquery.js"></script>
	<script>
		$("h1").css("color","red");  //将选择器$("h1")找到的元素的样式color设置成红色
	</script>
</body>
```

**获取命名为title元素的中的文字**

``` html
<body>
	<h1 class="title">hello jquery</h1>
	<script src="script/jquery.js"></script>
	<script>
		var txt = $(".title").text();
		console.log(txt);
	</script>
</body>
```

**更改img图片的路径**

``` html
<body>
	<img class="pic" src="">
	<script src="script/jquery.js"></script>
	<script>
		$(".pic").attr("src","images/0.jpg");
	</script>
</body>
```

*  ".nav"可以找到class名为nav的元素
*  ".nav li"可以找到class名为nav中的所有li元素
*  ".nav li:eq(1)"可以找到class名为nav中，左右li的第二个元素，这里需要注意的是元素的索引（编号）从0开始，所以1代表第二个元素。

**给予.nav li:eq(1)跟(activs)命名的css样式**

``` html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
    <title>Document</title>
    <style>
        .active{
            background-color: red;
        }
    </style>
</head>
<body>
	<ul class="nav">
		<li>香蕉</li>
		<li>苹果</li>
		<li>鸭梨</li>
	</ul>
	<script src="script/jquery.js"></script>
	<script>
		$(".nav li:eq(1)").addClass("active");
	</script>
</body>
</html>
``` 
* click鼠标点击事件
* attr更改src
* console.log()在控制台输出
* $(this).index();索引


**索引案例**
``` html
<body>
    <ul>
        <li>1</li>
        <li>2</li>
        <li>3</li>
    </ul> 
    <img src="images/0.jpg">
    <script src="script/jquery.js"></script>
    <script>
        var arr = ["images/0.jpg","images/1.jpg","images/2.jpg"];
        $("li").click(function(){
            var i = $(this).index();
            var url = arr[i];  //获取图片的地址
            $("img").attr("src",url);  //将图片的src属性设置成数组中指定的图片地址
        })
    </script>  
</body>
```

* mouseenter移入事件
* mouseleave移出事件
* addClass给元素添加class命名
* removeClass移除给元素添加的class命名
* hover鼠标划过事件
* pageX页面的x轴坐标
* pageY页面的y轴坐标
* hide隐藏元素，加了秒数会从右下方向左上方消失
* show显示隐藏的元素
* slideUp从下到上逐渐消失
* slideDown从上到下逐渐显示隐藏的元素
* fadOut逐渐透明的慢慢消失直到隐藏元素
* fadeIn透明度的方式显现出来 
* animate自定义动画 


**自定义动画案例**


``` js
$("button").click(function(){
    $(".box").animate({marginLeft:"300px",marginTop:"100px"},500);  
});
```

* val方法不仅可以获取元素的value属性值，还可以用来设置属性值
* append添加新元素
* remove删除元素
* delegate绑定事件

**绑定事件案例**
``` js
<body>
	<input type="text">
	<button>添加</button>
	<ul class="fruits">
		<li>香蕉</li>
		<li>苹果</li>
		<li>鸭梨</li>
	</ul>
	<script src="script/jquery.js"></script>
	<script>
		$("button").click(function(){
			var val = $("input").val();
			var newli = "<li>"+val+"</li>";
			$(".fruits").append(newli);
		})
		$(".fruits").delegate("li","click",function(){
			$(this).remove();
		})
	</script>
</body>
```
* siblings方法可以获取同级的其他元素，这样我们就可以继续完善我们图片切换的效果了。