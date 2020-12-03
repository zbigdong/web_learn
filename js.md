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
## this

不同场合this的指向不同
		window对象简介  
			浏览器窗口对象，代码执行的时候所有的一切都是包含在窗口对象下的. 

构造函数一般用于函数实例化对象

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

# 

​	