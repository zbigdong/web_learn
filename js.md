# Javascript

Javascript简介（是什么）
	谁在哪什么时候用多长时间开发的，是一门什么样的语言

​	美国 布莱登·艾奇  1995年 10天	
​	javascript  是一门动态的、弱类型的、解释型的脚本语言
​	动态：只有在执行的时候，才能确定数据类型
​	弱类型：变量数据的类型不是确定的，可以随意的进行改变；
​	解释型：相对编译型来说，编译型计算机在执行之前需要把程序进行编译，完事之后才执行
​		解释型，不需要编译，执行的时候，一行一行去解释执行；
​	
​	脚本：一般只要是脚本语言，都代表可以嵌在其它的语言当中进行执行；

​	起初叫什么  后来怎么叫Javascript  （了解）
​		livescript  sun 开发了java    借助java的名字火了一把   
​		把livescript 改为 javascript
​		java和javascript

1	html    负责结构
2	css     负责样式
​3    js      负责行为（动态效果）

TB PB ZB YB

# Js组成部分

1. ECMAscriot 负责js的语法部分
2. DOM document object model 文档对象模型（操作元素）
3. BOM browser object model 浏览器对象模型（操作浏览器）

# Js执行特点

从上到下一行一行执行，每句都要进行;结尾，分号不是必须的

js可以写行内js必须要链接事件

# 变量



**什么是程序？什么是进程？**

​	程序：代码的集合，一般指的是文件，程序是静态的
​	进程：运行的程序，就被称作进程，进程是动态的


​		

​	程序其实就是一个输入  运算   输出的过程
​	那么我们要对一个数据进行运算，然后进行输出，这个数据就需要有一个东西去保存
​	这个东西，就是我们所说的变量，本质上是一个容器（内存空间）；



## 1、定义变量，

   先定义后使用， 变量的初始化  （var和不写的区别）   变量的本质，内存的结构图 

​	定义变量使用 var关键字   先定义后使用，定义好之后，可以给变量赋值（存值）
​	如果定义变量不使用var，那么变量必须要赋值，不赋值报错未定义；
​	建议，我们在使用的时候，都带上var去定义变量。

## 	2、变量的命名规范

（组成，大驼峰，小驼峰，下划线）

​		变量的名字由：数字  字母  下划线 以及 $组成
​			      不能以数字开头
​			      不能和关键字以及保留字同名
​	
​			      变量名我们一般要见名思意


​		大驼峰：变量名所有的单词首字母大写                      var ClassNumber        
​		小驼峰：变量名第一个单词首字母小写，其它的大写	      var classNumber  前端人员最常用的是这个，只有特定情况用大驼峰；
​		下划线：单词和单词之间用下划线连接	              var class_number	



## 	3、关键字和保留字

​		javascript的关键字

```js
	break   case   catch   continue   default   delete   do
		else   finally   for   function   if   in   instanceof
		new   return   switch   this   throw   try   typeof
		var   void   while   with
```


​		javascript的保留字

```js
abstract   boolean   byte   char   class   const   debugger   double
		enum     export    extends       final   float   goto       implements
		import     int       interface     long    native  package    private
		protected  public    short         static  super   synchronized
		throws    transient  volatile 
```

#  数据类型

## 1、数据类型

（存储的数据的类型）

​	基本数据类型和对象(复杂)数据类型
​		基本数据类型（值类型）
​			number    string   boolean   undefined   null

​		对象数据类型（对象类型，后续）

## 2、基本使用场景

​	**数值类型**    整数   小数   科学记数法  **2进制(0b)   8进制(0)   16进制(0x)**


​		

​	**字符串**      单引号或者双引号包含  空字符串  和  空白字符串
​	布尔	    true或者false
​	**undefined**   定义的变量没有赋值
​	**null**        定义的变量赋值为null(一般是对对象进行初始化使用或者是删除一个对象的时候用到)

## 3、数据类型的判断 	

```
typeof判断
​	typeof的结果是什么类型
​		Typeof typeof 5
​	typeof的判断基本数据类型的特殊情况
​		null
```



## 初始变量

约定成俗

```js
var sum = 0;

var carName = 'car'
var isClose = ture;
//var a = undefined;基本不用，不能叫做初始化 
var dog = null; //代表要存储关于狗的对象
```



# 运算符和表达式

​	什么是运算符  什么是表达式   

运算符：参与运算的符号
表达式：由变量或常量和运算符组成的式子   表达式是有值的*****

1、算术  算术表达式

取余的作用：
	1、可以拿到余数
	2、可以拿到一个范围
	任何的一个数对78取余，余数永远是在0~77之间  包含0和77      （num）%78 + 1

 

​	++ -- 作用及注意事项
​	自增自减运算符，这个运算符只能和变量组成表达式
​	**++在后**，先赋值（先把a的值赋值给表达式）  后++ （后让a的值+1）
​	**++在前**，先++(先让a的值+1)  后赋值（后把a的值赋值给表达式）

​	a++
​	++a
​	a--
​	--a

# 数据类型转换

## 	1、数据类型强制转换

### 		**Number()  **NaN

  **强制将一个其它类型数据转化为数字类型，转不了就是NaN**	

​	   通常情况下是用来转字符串的
​		如果字符串整体来看是一个数字，那么就转化为这个数字
​		如果字符串整体来看不是一个数字，那么就转化为**NaN**
​		如果字符串是一个特殊的空字符串或者空白字符串，那么转化为0		

### 	**String()    **

**强制将一个其	它类型数据转化为字符串类型、**

​		转化字符串没有什么特殊，只要给我东西，那么就会把这个东西原样变为字符串输出；

### 		**Boolean() **

强制将一个其它类型数据转化为boolean类型

​	转化数字的时候，除了0是false,其余都是true;
​		转化字符串的时候，除了空字符串是false,其余都是true
​		转化undefined和null都是false;

​		怎么快速将一个字符串‘23’转化为数字23

## 2、数据类型隐式转换

各种类型在适当的场合会发生隐式转换

​		

```
		var a = 5;
		var b = a + 9;
        var b = a + false;
```

​	主要是运算过程和判断过程中

## 3、数据类型手动转换

（其实就是在字符串当中提取数字）

​	parseInt()
​	parseFloat()



# 运算符和表达式

​	

赋值    把 = 右边的值  赋值给 = 左边的变量    = 左边一定是变量

​	var a = 1
​	var b = 2;

​	a = b;

​	a = a + b;

​	=   
​	+=  -=  *=  /=  %=   复合赋值运算符    a+=b   ===   a = a + b;

、比较（条件运算符） 和 表达式 

	>  <  >=  <=  ==  !=  ===  !==

​	==          判断的是值是否一致
​	=== 	    判断的是类型和值是否都一致  都一致才会为true  

4、逻辑运算符   通常用在多个条件表达式的连接
	&&  ||  ! 

​	**&&  放在两个值    && 前面为真 整个表达式的值是后面的值   前面如果是假，整个表达式的值是前面的值**
​	a  = 0 && 100; // 0

​	**||  放在两个值    || 前面为真 整个表达式的值是前面的值   前面如果是假，整个表达式的值是后面的值**

​	通常情况下  && || ！都是和条件运算表达式在一起使用
​	&&   一假则假
​	||   一真则真
​	！   非真即假  非假即真

5、三目运算符   三元    问号冒号表达式
	? :
	a > 0 ? 10 : 100; 
	先执行第一个表达式（也就是？前面的表达式），看看这个表达式是否为真

​	如果第一个表达式的值为真，那么把冒号前面的值，赋值给整个表达式
​	如果第一个表达式的值为假，那么把冒号后面的值，赋值给整个表达式；

## 快速number化

怎么快速将一个字符串‘23’转化为数字23      '23' - 0;

​		Number('23');
​		**'23' - 0;**
​		parseInt('23');
​		parseFloat('23');

# 判断语句单多分支

## IF

```js
if(){

}

else if{}

else if{}

else{}
```

## Switch

```js
switch(num){
    case num=1:alert("1");
    break;
    case num=2:alert("2")
    break;

}
```

## **FOR**

```
for(一般初始化表达式；一般都是条件表达式；自增自减表达式){

​	循环体（代码块）
​	}
```

## break和continue关键字

continue;//结束当前循环（continue以下的代码不会执行了，从下一次开始继续）
break;//在循环当中，跳出离它最近的那一层循环。如果是多层循环要注意

```js
//圣诞树
for(var i = 0; i < 7; i++){
   //为了打印空格
   for(var j = 0; j < 6 - i; j++){
      document.write('&nbsp;');
   }
   
   //为了打印*
   for(var k = 0; k < 2*i + 1 ;k++){
      document.write('*');
   }
   
   document.write('<br>');
   
}
for(var i = 0; i < 8; i++){
			for(var j = 0; j < 4; j++){
				document.write('&nbsp;');
			}
			for(var j = 0; j < 5; j++){
				document.write('*');
			}
			document.write('<br>');
		}
```



# 数组

数组概念，作用，定义

​		数组： 是一个具有相同类型或者不同类型的数据有序集合；

```js
	为什么： 因为我们想要一次性拿到很多个数据，如果没有数组，就得定义很多的变量去存储

数组length，索引（下标）
	只要定义一个数组，数组里面就会有一个默认的属性叫length,它代表着数组的长度
	索引也被称作下标，通常情况下只要我们知道了索引，就可以拿到这个数组对应的这个索引的值		

数组（数组的不同位置 增  删  改  查）
	在数组的末尾加一个数
	在数组的头部加一个数
	在数组的中间加一个数
	删也是三个位置
    arr = [1,2,3,4,5,6]
arr[6]='c'
for(var i = arr.length-1;i>=0;i--){
    if(i>=3){arr[i+1]=arr[i]}
    if(i==3){arr[3]='b'}

}
// arr[0]='a';
console.log(arr)//[1, 2, 3, "b", 4, 5, 6, "c"]
    //arr.length--
移位；
	改和查知道了下标怎么都可以玩，但是不知道下标的情况下，我们需要去遍历以下数组
```
# 函数

**函数只能返回一个值**

```js
return [max,min];//return只能return一个值
            
//          return max,min;// 这样的写法是错误的，不能return多个值；
```

**函数传参：分为传基本数据类型和对象数据类型**

​       传基本类型和对象类型不一样:基本数据类型传进去后,函数外和函数内操作的不是一个值;
​       所以当传递基本数据类型的时候,函数内部运算后的结果我们需要返回;
​       
​       但是如果传的是对象类型(数组),那么函数内部和外部操作的是同一个数据(数组),因此,
​       函数内部对数组所有的操作就相当于操作外部的一样.所以运算完之后不需要返回,外部一样
​       看到发生了变化;

## 作用域

全局变量和局域变量，块级

###   程序执行过程

当中内存是怎么表现的

栈结构：先进后出

堆结构：随意增删；

1. 程序执行的开始：首先创建全局环境，并且这些环境都是在栈里面进行管理的；
2. 创建完全局环境之后，会把程序中所有的全局变量收集起来并且执行开辟空间；
3. 接着函数调用的时候才会创建环境，并且手机所有的局部变量执行开辟空间；
4. 当函数执行完成以后，也就函数返回值之后函数执行完成此时函数的环境会从站中弹出代表函数环境被销毁也就是释放内存；
5. 当整个函数执行结束以后全局环境最后才会弹出栈也就是销毁了全局把环境释放全局环境占用好的内存；

## 预解析

变量   带var和不带var: 预解析只会解析带var的变量，如果不带var，不进行预解析

虽然解析变量之后但是变量的值不会被解析上去；

函数   字面量和表达式函数关系

				function f1(){}            如果是这种写法；函数整体会提升
				var f1 = function(){}	   如果是这种写法；只会提升var f1; 不会提升函数的表达式；
# IIFE

Immediately Invoked Function Expression，意为立即调用的函数表达式（匿名函数自调用）
	作用？

```
(function(){

})();
```

定义的时候就一起调用了，不会发生与解析

匿名函数自调用只能执行一次

通常用来做一些项目的初始化

## 匿名函数自调用

1. 封装代码实现不把代码暴露出去

   juqery包装；

   ```
   (function(window,undefined){
   
   })(window);
   ```

   

2. 可以防止外部的命名空间被污染；

### Arguments  

函数实参伪数组

在每个函数当中，都会有一个实参的伪数组，这个东西是专门用来存储函数调用传过来的实参，即使你的函数定义当中没有形参，这个arguments当中也会存储你的实参；因此在js当中可以这么说，形参可有可无；

通常情况下我们可**以根据这个arguments伪数组的长度去让**一个函数表现出不同的功能，函数定义当中肯定是一个if else判断

## 回调函数

函数是我定义的   我没有调用    最终执行了~  

事件          本来就是一个方法或者函数   写回调函数
定时器
ajax
生命周期回调函数

# 对象

**对象的创建方法**

​	a)	字面量创建
​			var obj = {
​				name:'zly',
​				age:32,
​				sing:function(){};
​			}
​	b)	New Object
​			var obj = new Object();
​	c)	工厂函数模式

**对象的操作及遍历（增删改查）**

var a = 'gender';
		var obj = {};
		obj.name = 'zs';
		obj["age"] = 30;
		obj[a] = 'male';


		delete obj.name
	
		obj.name = 'lisi';    有则更改无则增加
	
		var name = obj.name;
	
		读   方式 .语法  []语法
		写   
		注意点：.语法和[]语法   还有变量
		遍历   for in循环进行遍历对象


		for(var key in obj){
	
			console.log(key,obj[key]);
	
		}
# this

不同场合this的指向不同
		window对象简介  
			浏览器窗口对象，代码执行的时候所有的一切都是包含在窗口对象下的. 

构造函数一般用于函数实例化对象

## var that =this;

this指的是当前的对象。 that是一个临时的变量，用于保存当前对象的this状态。（that可以随便取名

## new

new关键字实例化对象的	
		1、开辟内存空间
		2、this指向该内存
		3、执行函数
		4、生成对象实例

对象的本质就是一块内存

## 原型对象和原型链

```
Person.prototype.sing
```

![image-20201201164831630](D:\web_learn\image-20201201164831630.png)

### 原型链概念

对象在调用方法或则属性的时候会首先从自己的空间中去找，如果找不到去直接的原型空间中寻找（自己的构造函数的对象）。

apply 和 call可以让一个对象使用另一个对象方法：

然提供一个实例去调用windowD方法

函数或则方法.apply或则.call

 var result = add.apply (cat1,[10,20]);

使猫这个对象调用add加这个函数；

##  内置对象JSON

JSON是js当中的一个内置对象，里面封装了对json格式数据的操作方法；
json是一种数据格式，是前后端目前数据交互的主要格式（xml）
		

json通常情况下说的是字符串也叫json串
在前端json串的格式就是对象或者对象的数组，只不过要把这些数据转化成字符串形式；

在前端json串的格式就是对象或者对象的数组；

###   JSON对象的方法: 

parse， stringify



## Math工具对象

```js
 //round, floor, radom, cell, max  min  PI  pow
    console.log(Math.floor(1.23));//1
    //floor向下取整
    console.log(Math.ceil(1.2));//2
    //向上取整
    console.log(Math.round(1.5))//2
    //四舍五入
    console.log(Math.random())
    //随机数返回0-1之间的数包含-0不包含1；
    console.log(Math.max(1.23,432,54,23,2))//432
    console.log(Math.PI)//3.1415...
    console.log(Math.pow(2,3))//8的四次方
    console.log(Math.sin(Math.PI/2))//三角函数在math中全部要使用弧度而不是角度；

    // //随机数点名
 
    function getrandom(min,max){
        return Math.floor(Math.random()*(max-min+1)+min)
    }

    console.log(getrandom(1,20))
  //验证码
    function getrandomcode(){
        var acl= 'qwertyuiopasdfghjklzxcvbnm1234567890'
        code = ''
        for(var i = 0;i<4;i++){
            code += acl[Math.floor(Math.random()*acl.length)];

        }
        return code
    }

    console.log(getrandomcode())
```

## Date日期对象

	1.	Date对象的方法
​		var date = new Date();
​		console.log(date);
​		console.log(date.getFullYear());
​		console.log(date.getMonth());
​		console.log(date.getDate());
​		console.log(date.getHours());
​		console.log(date.getMinutes());
​		console.log(date.getSeconds());
​		console.log(date.getYear());//已经废弃
​		console.log(date.toLocaleTimeString());
​		console.log(date.toLocaleDateString());
​		console.log(date.getTime());//1970 年 1 月 1 日之间的毫秒数

​	案例：
​	1. 格式化日期
​	2. 封装函数实现格式化日期

## 包装对象

​	基本数据类型也可以使用.调用方法   

## 数据类型分类图

![数据类型分类脑图](D:\web_learn\数据类型分类脑图.png)

## typeof和instanceof的用法

typeof在判断基本数据类型当中的 数字。字符布尔类型undefined以及函数的时候可以排上用场

但是当我们使用typeof去判断数组和对象以及null时候区分不出来，

instanceof可以判断一个数组对象是还是一个其他的构造函数的实例对象，通过判断这个对象使那个构造函数的实例对象可以区分出来

a==null 是专门用来判断null的 如果相同就是null

## 堆和栈的概念

​	**栈**     数据结构 （栈）          先进后出     **桶**          栈结构内存一般比较小，计算机自动分配内存，存取速度比较快  
​	**堆**     数据结构（链表）         随意进出                 堆结构内存一般比较大，底层是需要程序员自己分配（js做了封装，会自动分配），堆里面一般存储的都是一些比较复杂的占空间比较大的数据

**队列 **  **管道** 先进先出

堆和栈是内存的存数据结构，内存被开辟使用，就一定会被计算机回收（释放内存）

![堆栈和内存中数据展现](D:\web_learn\堆栈和内存中数据展现.png)栈  ➡ 堆

执行之后函数环境先释放内存，堆里面的值还在，但是没有人指向了，论为垃圾内存，直到下一次占用它再释放它。null是用来初始化和释放变量的

# **DOM**

​	     ![dom文档树](D:\web_learn\dom文档树.png)                                           

## window.onload

页面加载完成事件

window.onload = function(){

}等待页面完成的加载的程序

## DOm操作

获取DOM对象，操作DOM对象，事件绑定，操作元素属性
	1. 	### document.getElementById
	
			这个是document下的一个方法，通过id获取到相关元素  封装为dom对象返回
	​		如果没有id没办法获取

2.	### 点击事件
	
	​	**事件三要素  	事件源 （承受事件的对象）  	   事件           事件处理回调函数**
	​	事件处理三大步	获取事件源DOM对象   添加事件监听   书写处理回调
	​	事件写好之后可以重复触发执行；setA

3.	### 案例驱动: 修改元素的属性
	
	1. 点击按钮修改图片的路径
	
	2. 点击按钮修改a标签的路径
	
3. 点击按钮修改多选框选中
	
4. setAttribute和getAttribute的用法
		.语法和他们有啥区别？一个设置一个调用

	​	
	
		在操作元素属性的时候，.语法只能操作元素天生具有的属性，如果是自定义的属性，通过.语法是无法操作的；
		
		只能通过 setAttribute和getAttribute去操作；
		
		 **setAttribute**和**getAttribute**是通用的方法，无论元素天生的还是自定义的都可以操作；



​	**5、点击按钮修改p标签的背景颜色（通过改变类名实现）**

```js
className 
```

## 循环绑定事件+操作元素内容，操作元素内容

document.getElementByTagName Ie8以下不支持

document.getElementByClassName   querySelect 和 querySelectAll获取dom元素
	document.getElementById  只能通过ID去获取元素 并且只能获取一个元素返回
	document.getElementByTagName    只能通过标签名去获取，并且获取到是多个返回一个数组，哪怕标签只有一个也是数组
	document.getElementByClassName  只能通过类名去获取，并且获取到是多个返回一个数组，哪怕只有一个标签是这个类也是数组

**以上三个都比较局限：拿元素的时候只能通过指定的属性去拿**

### querySelect 和 querySelectAll

​		querySelect 和 querySelectAll也可以获取元素，但是他们和上面不同的是，他们根据**选择器**去获取。也就是说只要选择器能选择到，他们
​		就可以获取到，只要选择器写的对就可以获取到；

​	querySelect专门用来获取选择器选中只有一个元素；返回的是单个元素dom对象;
​	querySelectAll专门用来获取选择器选中多个元素，返回也是数组；

##   鼠标事件

 + style样式操作，操作元素样式
	1.	鼠标事件: 
		
		```js
		onmousemove/
		
		onmouseover/
		
		onmouseout/
		
		onmounseenter/
		
		onmouseleave
		
		onclick/onmousedown/onmouseup/ondbclik;
		```
		
		​	简单案例   点击按钮修改元素的宽高以及背景色；

##  兼容性封装设置读取内容函数

浏览器兼容性讲解 IE8是个分水岭

封装函数处理textContent和innerText的兼容性读写问题

## textContent及innerText的区别

​			·textContent 可以获取隐藏元素的文本，包含换行和空白
​			·innerText 不可以获取，并且不包含换行和空格

## 兼容性封装设置读取内容函数

	1.	浏览器兼容性讲解
	
		浏览器有很多：chrome和火狐   IE   Opera  safari  
		浏览器最终分为两个阵营： 高级浏览器和IE低版本浏览器   IE8是分水岭
	
		innerText   什么浏览器都认识
		textContent   只有高级浏览器认识  IE低版本不认识



		console.log(box.textContent);  
	
		当我们的用户既存在使用高级浏览器的也有使用IE低版本的，那么此时，如果想要使用textContent 必须兼容性处理




	2.	封装函数处理textContent和innerText的兼容性读写问题

## keyup & keydown & focus & blur  

	1.  keyup，keydown事件       一般用的都是keyup事件，它能够确保键盘事件只执行一次；
	2.	keycode     存在于事件对象当中，也就是我们回调函数的第一个形参；这个对象不是我们创建，当事件发生的时候，系统会创建好
			这个事件对象，并且传参调用；事件对象当中包含了和事件相关的一切；

3. focus，blur事件

   # 节点

## 子节点和子元素

​		childNodes    拿到的是某个元素的子节点：包括元素子节点和文本子节点，如果有注释还有注释节点； 
​		children
​			子节点:childNodes (儿子节点):
​			高级浏览器: 元素,文本(文本,空格,换行),注释
​			低版本浏览器: 元素,文本(不包括空格和换行),注释
​			子元素 children(儿子元素):
​			高级浏览器:元素
​			低版本浏览器:元素,注释



## 父节点和父元素

​	parentNode
​	parentElement
​		父节点:parentNode 其实就是父元素(标签) 所有浏览器都能使用
​	 	父元素:parentElement 父标签   所有浏览器都能用

## 获取其它节点：

​		第一个子节点        都认识   firstChild
​		第一个子元素节点    只有高级浏览器可以使用  firstElementChild
​		最后一个节点      都认识   lastChild
​		最后一个元素节点  只有高级浏览器可以使用  lastElementChild
​		上一个兄弟节点    都认识  previousSibling
​		上一个兄弟元素节点  只有高级浏览器可以使用 previousElementSibling
​		下一个兄弟节点    都认识 nextSibling
​		下一个兄弟元素节点  只有高级浏览器可以使用  nextElementSibling

## 创建节点的三种方式

Documet.write()   根本不用
			 * 第一种创建节点的方式:document.write();
			 * document.write()只能在页面加载的过程中使用,如果当页面加载完后,再使用会将其它的dom干掉
				

Obj.innerHtml  

Document.createElement('想要创建的元素名') 
元素对象.appendChild(被追加的元素对象);

##  节点常用方法

​	

节点：  文档当中都是节点   元素  文本 属性  注释。。。。。。。
节点的增删改查



* 以下方法都是父元素调用,操作子元素
* 插入节点: insertBefore(新节点,参照节点);
* 替换节点: replaceChild(新节点,被替换的节点);
* 删除节点: removeChild(被删除的节点);
* 追加节点：appendChild(被追加的节点)；
  节点.remove**（pc端 ie不支持）** 
  案例：使用列表演示节点的增删改查

## 事件绑定和解绑 

​	dom0事件解绑  本质上就是把事件函数和事件对象的事件属性断开指向；
​	box.onclick = null;

Dom2事件绑定和解绑   
   可以添加同一类事件多次
   高级浏览器和ie绑定方式（兼容封装）

## 事件流（事件传播）

	1. 捕获事件流（网景）   最终很少用几乎不用
	2. 冒泡事件流（ie）     最终我们所用的事件传播都是冒泡



3. 标准DOM事件流     //这个是我们现用的最标准的事件流，里面包含三个阶段： 有捕获  再去获取元素    然最后冒泡

## 阻止事件冒泡

```js
event.stopPropagation();
```

事件冒泡的好处就是可以进行事件委派（事件委托，事件代理）

事件委托用法，
	什么时候用：出现新添加的东西，并且新添加的东西要和老的拥有同样的行为；此时我们就想事件委派；

​	事件委派的做法： 给爹添加事件，不给元素本身添加，事件发生后通过爹去找，真正发生事件的元素进行处理；

好处，原理

onmouseenter onmouseleave       如果是一个父子元素模型，对父元素添加移入和移出，当鼠标移入父元素里面的子元素的时候，事件并没有移出然后再移入。也就是说事件元素没有切换；

onmouseover onmouseout 这两对之间的区别
				 如果是一个父子元素模型，对父元素添加移入和移出，当鼠标移入父元素里面的子元素的时候，事件会移出然后再移入。也就是说事件元素会有切换；**事件委派的时候，必须使用这一对；**

## 事件委派

```js
tBodyNode.addEventListener('click',function (event){
    event = event || window.event;
    var aNode = event.target
    // let trnode = this.parentElement.parentElement;
    //
    // tBodyNode.removeChild(trnode);
})
```

##  window对象是bom的顶级对象

	1.  window对象概念，使用
		function  add(){
		}
		add()
		window.add()
	2.  location  window.location可以让用户获取当前页面地址以及重定向到一个新的页面。
			window.location.href   可以读也可以写，写的时候相当于转向另外一个页面
	
	    history   对象包含浏览器的历史记录，window可以省略。这些历史记录以栈（FIFO）的形式保存。页面前进则入栈，页面返回则出栈。
	    navigator 是一个只读对象，它用来描述浏览器本身的信息，包括浏览器的名称、版本、语言、系统平台、用户特性字符串等信息。
	    screen    提供了用户显示屏幕的相关属性，比如显示屏幕的宽度、高度，可用宽度、高度。
			
	3.  window.onload
	    window.onresize   //浏览器窗口发生改变，就会执行这个事件；
## event 对象

	1.  event概念，作用
		系统给我们封装的，任何事件都会有这个event对象，就是回调函数的第一个形参；
	2.  event兼容性处理
	3.  event.target || event.srcElement作用
	4.  clientX & clientY     拿的是鼠标相对视口的 水平距离和垂直距离   相对的是视口的左上角（以视口左上角为原点）
	        pageX pageY           拿的是鼠标相对页面的 水平距离和垂直距离   相对的是页面的左上角（以页面左上角为原点） 
	    offsetX   offsetY     拿的是鼠标相对自身元素的 水平距离和垂直距离   相对的是自身元素左上角（以自身元素左上角为原点）

# 定时器

单次定时器： 一般用来做延迟效果   定时炸弹 
		    案例 求出结果延迟5秒打印  

```js
timer = setTimeout(function(){
    console.log('5');
},5000);
clearTimeout(timer)
//清除定时器
```

多次定时器： 和循环类似    闹钟
	    案例  每隔3秒打印i love you!

```js
timer = setInterval(function(){
console.log('i love you');
},3000);
//同样可以清除
clearTimeout(timer)
```

清除定时器：
	    清除单次定时器
	    清除多次定时器

input属性有个叫做disabled

## 元素的大小和位置

### Offset系列    只读 

​			offsetWidth      拿的是盒子   内容 + padding + border的宽；
​			offsetHeight   	 拿的是盒子   内容 + padding + border的高；

​		offsetLeft       拿的是元素的偏倚量：可以认为就是拿的定位left值
​		offsetTop        拿的是元素的偏倚量：可以认为就是拿的定位top值

​		案例：盒子左右摇摆


​	

### 	Client系列    只读

​		**clientWidth**      拿的是盒子   内容 + padding的宽；
​		**clientHeight**     拿的是盒子   内容 + padding的高；

​		**clientLeft**       拿的是盒子左边框大小；
​		**clientTop**        拿的是盒子上边框大小；
​		 
​		视口宽高求法   
​				document.documentElement.clientWidth
​				document.documentElement.clientHeight

  

### 	Scroll系列

​		scrollWidth   只读  
​				//当内容比盒子小的时候，拿的是盒子的clientWidth

//					//当内容比盒子大的时候，拿的是内容的offsetWidth + 盒子的一侧内边距； 
			scrollHeight  只读
					//当内容比盒子小的时候，拿的是盒子的clientHeight
//					//当内容比盒子大的时候，拿的是内容的offsetHeight + 盒子的一侧内边距；

​		scrollTop     可写
​				//拿的是盒子内容向上滚动的距离
​		scrollLeft    可写
​				//拿的是盒子内容向左滚动的距离


​		滚动条的高度 / 屏幕的高度 = 屏幕的高度 / 内容的高度 = 滚动条的移动距离 / 内容的滚动距离

​	元素的大小：宽和高的获取；
​	以后我们拿元素的宽和高 先看元素有没有边框   如果没有边框    那么clientWidth和offsetWidth是一样的
​				如果有边框，看你需要不，需要的话就用offsetWidth 不需要就用clientWidth;
​				scrollWidth几乎不用；

## 初始包含块

document 初始包含块 html body 其次是元素

## 初始包含块及系统滚动条的控制

​	

​    html和body这两个元素overflow的scroll属性，控制着系统的滚动条
​    系统的滚动条有两个，一个是body身上的  一个是document身上的。我们平时看到的那个滚动条
​    是document身上的。，如果我们想要控制系统滚动条哪个显示哪个关闭分以下情况：

​    1、单独的给body或者html 设置overflow:scroll  滚动条打开的全部都是document的

​    2、如果两个元素同时设置overflow属性，body设置的是scroll,html设置是hidden,那么
​    document的滚动条被关闭，body身上的滚动条会打开。相反，body身上被关闭，document身上的被打开。

​    3、如果两个元素同时设置overflow:hidden；那么系统的两个滚动条全部被关闭；

​    4、**如果两个都设置overflow:scroll,那么html会打开document身上的，而body会打开自己身上的滚动条；**



###     由此我们也引出如何禁止系统的滚动条：


```html
html,body{
	height:100%;    //这个属性加上只是为了让设置的overflow:hidden;更有说服力，只有内容超出才会被掩藏或者出现滚动条
			//如果不设置，那么body和html高度将由内容自动撑开，也就是说body当中的内容永远不会溢出。
	overflow:hidden;
}
```

在基础的拖拽事件上添加边界问题

当元素在四周的时候不能超出范围做出范围界定

计算元素到视口上方和左边的距离getBoundingCllientRect()只能读不能写

主要是检测什么时候盒子碰撞

使用图片切换模拟盒子碰撞

##  **wrap**

包裹器名字

## 居中

```css
left: 50%;
transform: translateX(-50%);
```

# 总结

## ECMAscript ：

### 1、js的写法    三种

```
	<input onclick="alert()">
​	内嵌
​	外链   <script src="文件路径"></script>
```



### 2、变量  变量的本质（内存）   

​	   变量的命名规范 
​	   变量的初始化    var a  = 10;    ===   var a;   a = 10; 

	   交换两个变量的值；

### 3、数据类型	

​		按大的类： 基本 和 对象（引用）
​		基本： 数字  字符串 布尔值   undefined  null;   主要关注undefined  null  理解清楚什么意思、

​	对象：  数组（既是数组又是对象，数组操作元素，对象操作属性）
​	        函数 (既是函数又是对象，当函数去用，是为了执行某个功能，当对象去用是为了操作属性）
​		对象（Object的实例对象 还有 构造函数的实例对象）
​		内置工具对象   Math Date JSON  
​		包装对象   String   Number   Boolean
​		正则对象  

### 4、运算符和表达式

​		运算符：  算术 ++  --   赋值  比较  逻辑  三目运算符   ？：
​		转化     显示   隐式   手动

		0   false   '0' true    e = a || b || c || d

### 5、语句结构： 

 顺序   分支   循环
		水仙花
		质数
		打印图形
		打印乘法口诀表
		break和continue的区别
		while和do..while的区别

### 6、数组：

​		概念：
​		数组的定义：   字面量    构造函数 new Array(1,2,3)     Arrary(1,2,3)       Arrary(3);
​		数组的增删改查  遍历
​		二维数组（了解）
​			（原生js通过下标操作）
​			冒泡排序
​			数组去重
​			数组合并
​			数组翻转

### 7、函数

​		概念
​		定义：   字面量   构造函数定义     函数表达式定义 
​		函数的三要素及如何封装函数（分成四类）   return;   函数当中才会有return,在函数内部函数执行碰见了return就立马结束，函数内部之后的代码不再执行
​		全局和局部（作用域）  作用域链
​		预解析 ：   所有带var的遍历还有所有的函数  都会进行预解析   做变量提升    优先提升函数  函数重名覆盖   再解析变量，变量重名忽略
​		****  函数的执行过程  及  整个程序执行的时候内存变化
​		回调函数     自己定义  自己没调   执行了
​		arguments
​		IIFE 匿名函数自调用
​		this

### 8、对象

​		object实例对象
​		概念：
​		定义：  字面量   构造函数   工厂函数  
​		操作：  **********   .语法   []语法    注意：变量

​	定义特定的构造函数实例化对象

​	构造函数的概念：
​	构造函数的作用：   new关键字都做了什么     画图
​	函数当普通和构造函数区别（this）


​		

​	原型对象： 隐式原型   显式原型
​		  原型对象的作用：共享空间  节省资源 
​	
​	原型链    实例对象找属性的过程

​	apply和call  改变方法或者函数  的执行者

​	typeof 和 instanceof的区别和用法     ==判断null 


​	

​	值类型和对象数据类型   ************************

```js
		var a = 10;
​		var b = 15;
​		a = b;
​		a = 20;


​			

​		console.log(a,b);

​		var arr = [12,13]
​		var arr1 = arr;

​		arr1[0] = 55;

​		console.log(arr);
```

### 9、内置的对象		

​		  	Math
​				abs   floor  ceil  round  PI  random  max  min  pow  sin
 			JSON

​			JSON.parse    JSON.stringify

​		Date
​			年  月   日  时  分  秒  星期      1970年到现在的毫秒数

​		包装对象

​		正则

### 10、 数组和字符串方法：

​							  	

	   		数组：    push  pop  shift  unshift  splice   join     reverse  concat   sort   
	  
			字符串：  charAt   indexOf  split   length       [索引]进行操作 只能读不能写  
### 11、DOM

​		节点：
​			增删改查：
​				怎么去找节点
​					childNodes
​					children
​					parentNode
​					parentElement
​					

​				元素.firstChild
​				元素.firstElemetChild  
​					last
​					previousSiblings
​					nextSiblings

​			增加节点   三种

​			父级元素操作子元素：
​				insertBefore
​				appendChild
​				removeChild
​				replaceChild	
​			createElement

​	JS操作元素
​		获取dom对象
​		事件添加    dom0   dom2
​			    事件对象
​				event 
​				event鼠标位置
​				event.target 
​				event.stopPropagation
​				event.preventDefault	
​					
​			    事件流
​			    事件冒泡
​			    阻止事件冒泡
​			    事件委派
​			    事件当中的this
​			    事件当中阻止浏览器默认行为

​		JS操作元素属性
​			    	dom元素.属性
​			    	setAttribute
​			    	getAttribute

​		JS操作元素内容

​				innerText
​				textContent
​				innerHtml

​		JS操作元素的样式

​			        元素.style.样式       JS操作的样式全是行内
​				元素的宽高和样式读取：
​					client系列
​					offset系列
​					scroll系列



​		DOM当中所有的案例;
​			    排他
​			    开关

### 12、BOM	

​		window对象
​		     window.onload    window.onresize    window.onscroll 
​		location     href
​		screen       width  height
​		history      go  back   forward
​		navigator    navigator.appName

### 13、拖拽带自定义滚动条   

### 14、轮播图

CSS:
	

居中：
	文本在div居中心
		text-align:center
		line-height:DIV高度
	行内在div
		text-align:center
		line-height:DIV高度
	行内块在div
		position:absolute;
		left:0
		top:0
		right:0
		bottom:0
		margin:auto
		行内块必须设置宽高

​	块级在块级

​		position:absolute;
​		left:0
​		top:0
​		right:0
​		bottom:0
​		margin:auto
​		行内块必须设置宽高

​		position:absolute;
​		left:50%
​		top:50%
​		transform:translate(-50%,-50%);



​		position:absolute;
​		left:50%
​		top:50%
​		margin-left: -盒子的一半;
​		margin-top: -盒子的一半;
​		行内块必须设置宽高

transform 覆盖
transition  只会检测起始和结束


​	

设置文本溢出变为...

​	只能给块和行内块设置
​	行内不能设置，因为行内本来就是文本
​	overflow:hidden
​	text-oveflow:ellipsis;
​	white-space:nowrap;


​				

元素隐藏：
	display
	visibility
	opacity
	width
	height
	transform:  translateX  translateY  rotateY  rotateX   scale


​								
​				    

​	rotate(效果和rotateZ)是一样的


​		

3d变换如果不开启父元素3D空间：那么子元素设置了3D变换的元素，层级高出来