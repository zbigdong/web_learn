# js高级

## 复习-》BAT

### 基本数据类型

string number boolean null undefined

//基本数据类型的特点是 ： 一旦定义了值就不会轻易改变

### 引用数据类型

object array function

引用数据类型可以通过其赋值变量修改；

操作对象的属性不会导致变量指针改变

操作对象本身会导致指针改变

### 判断数据类型

typeof 返回值有几种

string number Boolean Undefined Function Object 

特殊null 和array的返回值也为object

面试题 如何使用js判断array和function、object

使用instanceOf; A instanceof  Array // 判断左侧的内容是否是右侧实例对象 右侧的值是不是左侧的构造函数

var c = {} var d = {}在堆内存产生两块内存

js只有堆内存 但是有一块类似于堆

栈内存给多大就多大；

# 函数

## 函数

      1. 函数也是对象
      2. 函数具备行为，可以被调用
      3. 用来减少代码量，复用，隔离变量，减少命名污染

## 函数分类

   1. 普通的函数

   2. 构造函数

      加工打磨一个构造函数产生的 对象

   3. IIFE(匿名函数自调用)//立即执行函数；

      ```
      (function(w){//w 是形参
      console.log('立即执行函数调用')
      })(r)//用于一次性的调用r是实参
      ```

   4. 回调函数(事件的回调，定时器的回调)

## 函数的this

```js
  1. 理解this：
     - 关键字
     - 变量
  2. this的指向问题
     - 函数this不是函数定义的时候决定的
     - 函数this指向谁看如何调用当前的函数
  3. this指向分类
     - 函数自调用： window
     - 构造函数(new function): 当前构造函数的实例对象
     - 对象.方法(): 对象本身
     - fun.call/apply(指定的对象): 指定的对象  用于修改this的指向（强制绑定this)
     that一般用于缓存this;

```

# js的继承

## 原型链继承

    1. 核心思想
        - 子类的原型 成为 父类的实例
        - Child.prototype = new Parent()
    2. 注意问题：
        - 以上的写法会导致子类的构造器属性丢失
    3. 解决问题
        - Child.prototype.constructor = Child

 




```js
       
         function Person(name, age) {
            this.name = name;
            this.age = age;
          }
          Person.prototype.showName = function () {
            console.log(this.name);
          }
          var person1 = new Person('kobe', 43);
```


​          子类的原型等于弗雷的实例

```js
      // 原型继承： 子类的原型 成为 父类的实例
      // Child.prototype = {constructor: Child}
      Child.prototype = new Person();
      Child.prototype.constructor = Child;
      // 定义一个child类
      function Child(name, age) {
        this.name = name;
        this.age = age;
      }
      
      var child1 = new Child('xiaoming', 18);
    
      console.log(child1);
      child1.showName();
```

## 借用构造函数继承(不是真的继承) 

```js
1. 核心思想
    - 让父类的方法在子类中执行
2. 注意问题：
    - 如果父类的方法在子类中直接调用，会导致在window对象身上添加了不必要的属性
3. 解决问题：
    - 使用call || apply
    - Parent.call(子类的实例对象， 参数)
    - Parent.call(this, 参数)
     function Person(name, age) {
        this.name = name;
        this.age = age;
    }
    Person.prototype.showName = function (){
        console.log(this.name);
    }

    function Child(name,age,sex){
        //chiild 的实例对象等于this
        Person.call(this,name,age)
        this.sex = sex;
        console.log(this);
    }
//子类的原型成为父类的实例
    Child.prototype = new Person();
    //构造器丢了人为添加
    Child.prototype.constructor = Child;
    c1 = new Child('kIk',12,'male')
```

## 组合继承

1. **核心思想： 原型继承 + 借用构造函数继承**


​    

# 原型

## 什么是原型对象

```js
1. 每个函数都有一个prototype属性，该属性指向的是原型对象(显示原型对象)
2. 每个实例对象身上都有一个__proto__属性，该属性指向的也是原型对象(隐式原型对象)
3. 构造函数的显示原型 === 当前构造函数实例对象的隐式原型对象
4. 原型对象的本质： 普通的Object实例***
原型对象一定有一个隐式对象方便系统查找 直到Object的原型对象的__proto__指向null;
```

## 什么是原型链

```js
1. 查找对象的属性的时候现在自身找，如果自身没有沿着__proto__找原型对象
2. 如果原型对象上还没有，继续沿着__proto__,直到找到Object的原型对象对象
3. 如果还没有找到返回undefined
4. 原型链： 沿着__proto__查找的这条链就是原型链
```



## 变量提升 & 函数提升

1. js引擎在js代码正式执行之前会做一些预解析的工作
2. 找关键字： var， function
3. 找到var以后将var后边的变量提前声明，但是不赋值 var a;
4. 找到function以后定义对应的函数，也就是说函数在预解析的时候已经定义完毕
5. 预解析： 全局预解析，局部预解析


​    

## 执行上下文

1. 理解： 
    - 执行上下文抽象的概念，代表了代码执行的环境，包含： **执行环境，变量对象，this，作用域链**
2. 流程：
    - js引擎在js代码正式执行之前会先创建一个执行环境(开发商批的地，工程队施工的环境)
    - 进入该环境以后创建一个变量对象(打地基)，该对象用于收集当前环境下的： **变量，函数，函数的参数，this**
        - 找关键字var ，function
    - 确认this的指向
    - 创建作用域链
3. 重点：
    - 执行上下文是动态创建的
    - 尤其是针对函数，每调用一次函数都会创建一次执行上下文



1. ```
    1. 执行上下文环境
       - js引擎在js代码正式执行之前会先创建一个执行上下文环境
       - 分类：
         - 全局执行上下文
         - 局部(函数)执行上下文
     - eval执行上下文
    
    2. 执行上下文的变量对象
       - js引擎进入执行上下文环境之后先创建一个变量对象
       - 该对象用于收集当前执行上下文环境中的： 变量，函数，函数参数，this
       - 确认this的指向
       - 创建作用域链
    3. 执行上下文栈
       - 作用： 用于保存执行上下文(变量对象)
       - 遵循规则： 先进后出，后进先出
       - 特点：执行上下文是动态创建的 ---> 针对函数，函数每调用一次就创建一次执行上下文，执行完就销毁
    ```
    
    

# new操作符都干了哪些事情

    1. 创建一个空对象
    2. 将this指向该空对象
    3. 执行函数
    4. 将执行的结果返回
    person.call(this,name,sex);

# 作用域

## 作用域理解

   - 抽象的概念
   - 用来决定代码执行的范围， 变量所属的范围
   - 作用域是代码定义的时候决定的
   - 作用域作用：
     - 隔离变量
     - 规定其之后的作用域链是什么样的，体现： [[scopes]]: 上一级作用域链

## 作用域链

   - 作用域链式一个数组结构
   - 该结构内保存的是一个个的变量对象
   - 作用域链什么时候创建的：在js代码正 式执行之前创建的

```
创建全局作用域--》预解析工作--》创建全局的执行上下文--》执行上下文环境--》变量对象{varename :undefined, this:window }

创建局部执行上下文--》局部变量--》局部作用域链

函数定义创建局部作用域--》函数自身有一个[[scopes]]:上一级作用域链last global;
```

# 闭包

闭包是一个存在内部函数的引用关系

该引用指向的是外部函数的局部变量（前提是内部函数使用了外部函数的局部变量）

## 作用

延长外部函数变量对象的生命周期

使用闭包能够间接的从函数外部访问函数内部的私有变量；

闭包形成的条件

1. 函数嵌套
2. **内部函数引用外部函数的局部变量**
3. 内部函数被使用：注意：函数变量提升的时候如果内部函数没有被使用，在与解析的过程中不会定义内部函数

## 闭包的优缺点

   - 优点： 延长外部函数变量对象的生命周期
   - 缺点： 延长外部函数变量对象的生命周期(占内存，如果不及时清除容易造成内存溢出，泄漏)

## 使用闭包的时候注意：   

   - 及时清除闭包
   - 让内部的函数成为垃圾对象 ---> 内部函数身上没有指针指向

## 进程

程序一次执行它占有独有的内存空间

## 线程

cpu调度的基本单位，是程序执行的完整流程

# 关系

一个进程中至少有一个运行的线程：主线程

一个进程中也可以同时运行多个线程，我们会说程序使多线程序运行的

一个进程内的数据可以供其中的多个线程直接共享

多个进程之间的数据不能直接共享

浏览器老版本firefox和老IE使单进程，chrome和新版ie使多进程

# js事件循环机制



1. js是单线程的 ---> 主线程--》会阻塞
2. 同步任务 || 异步任务
    - 同步： 1. 阻塞的 2. 同步是没有回调的
    - 异步： 1. 非阻塞 2. 异步有回调(用来通知当前异步任务执行的结果)
3. 定时器真的准时吗?不一样
    - 特例：定时器任务的后边有运算量大的代码段
4. 事件轮询机制：
    - 1. js任务都会在js的主线程执行
    - 2. 当开启一个异步任务的时候会交给对应的管理模块去管理
    - 3. 主线程继续执行后续的任务
    - 4. 管理模块接管的对应的回调，它会在恰当的时机将对应的回调放入callback queue中
    - 5. 当主线程上的所有同步任务执行完毕会通过 ‘轮询’的方式询问callback queue是否有可执行的回调
    - 6. 假如没有会反复询问
    - 7. 假如有可执行的回调将对应的回调钩到主线程执行
 5. 开发注意事项；
    - **不要在定时器任务之后放置运算量大的代码段**；

![事件循环模型](D:\web_learn\事件循环模型.png)

**永远不要放在定时器后面计算量较大的函数**

# 浏览器内核

**chrome，safari**；webkit

**firefox**:gecko

**ie**:Trident;



# 版本语法

# “use strict”

1. 变量声明必须写var，不写var报错
2. 禁止this指向window,如果构造函数忘记写new那么this不会影响全局
3. 禁止随意删除变量
4. 函数不能有重复的参数；

## let使用及特点

1. 块级作用域声明变量     
2. es6都是处于严格模式下的
3. let定义的变量不会进行预解析
4. let变量不允许重复定义

## const使用及特点

声明一个变量，变量的值无法更改，也是块级作用

const定义的变量不可以修改，而且必须初始化



## for in一般用于遍历对象

可以枚举原型的属性

#  string方法 **ES5**

### **功能 参数 返回值**

```js
var str = '1*234567890123A';
		console.log(str.charAt(8));//index
		console.log(str.charCodeAt(9));//index
		console.log(str.concat('iii'));//拼接
		console.log(String.fromCharCode(49));//unicode编码
		console.log(str.indexOf('2',3))//默认从0位置开始查找‘2’，第二个参数可以指定从哪开始；
		console.log(str.lastIndexOf('23'));//求字串位置,默认从末尾开始
		console.log(str.replace('1','**'));//替换字串
		console.log(str.localeCompare('12345678'));//比较大小
		console.log(str.match(/1/g));//找到匹配项返回数组
		console.log(str.slice(0,-4));//抽出字串
		//一个新的字符串。包括字符串 stringObject 从 start 开始（包括 start）到 end 结束（不包括 end）为止的所有字符。
		//结束可以使用负数
		console.log(str.split('2'));
		//以指定字符为间隔将字符串转化为数组
		console.log(str.substr(0,4));//后面的参数是长度
		console.log(str.substring(0,4));//后面的参数不允许是负数
		console.log(str.toLocaleLowerCase());
		//与 toLowerCase() 不同的是，toLocaleLowerCase() 方法按照本地方式把字符串转换为小写。只有几种语言（如土耳其语）具有地方特有的大小写映射，所有该方法的返回值通常与 toLowerCase() 一样
		console.log(str.toLocaleUpperCase());
		console.log(str.toLowerCase());
		console.log(str.toUpperCase());
		console.log(str.valueOf());
		console.log(str.toString());


```

字符串也可以使用下标进行操作；

# string方法 **ES6**

1.	includes(str) : 判断是否包含指定的字符串
   2. 	startsWith(str) : 判断是否以指定字符串开头
   3. 	endsWith(str) : 判断是否以指定字符串结尾
   4. 	repeat(count) : 重复指定次数

#  Array方法 **ES5**

​		console.log(arr.sort(function(a,b){
​			return b - a;
​		}))
​		语法：array.sort(fun)；参数fun可选。规定排序顺序。必须是函数。
​			注：如果调用该方法时没有使用参数，将按字母顺序对数组中的元素进行排序，说得更精确点，是按照字符编码的顺序进行排序。
​			如果想按照其他规则进行排序，就需要提供比较函数，该函数要比较两个值，然后返回一个用于说明这两个值的相对顺序的数字。比		较函数应该具有两个参数 a 和 b，其返回值如下：
​			若 a 小于 b，在排序后的数组中 a 应该出现在 b 之前，则返回一个小于 0 的值。
​			若 a 等于b，则返回 0。
​			若 a 大于 b，则返回一个大于 0 的值。
​			简单点就是：比较函数两个参数a和b，返回a-b 升序，返回b-a 降序
​		//注：原数组发生改变

​		

**不传参数**，将不会按照数值大小排序，**按照字符编码的顺序**进行排序；

```js
	var arr = ['General','Tom','Bob','John','Army'];
	var resArr = arr.sort();
	console.log(resArr);//输出   ["Army", "Bob", "General", "John", "Tom"]
	
	var arr2 = [30,10,111,35,1899,50,45];
	var resArr2 = arr2.sort();
	console.log(resArr2);//输出   [10, 111, 1899, 30, 35, 45, 50]
```

**传入参数，**实现升序，降序；

```js
	var arr3 = [30,10,111,35,1899,50,45];
	arr3.sort(function(a,b){
		return a - b;
	})
	console.log(arr3);//输出  [10, 30, 35, 45, 50, 111, 1899]
	
	var arr4 = [30,10,111,35,1899,50,45];
	arr4.sort(function(a,b){
		return b - a;
	})
	console.log(arr4);//输出 [1899, 111, 50, 45, 35, 30, 10]
```

根据数组中的对象的某个属性值排序；

```js
	var arr5 = [{id:10},{id:5},{id:6},{id:9},{id:2},{id:3}];
	arr5.sort(function(a,b){
		return a.id - b.id
	})
	console.log(arr5);
	//输出新的排序
	//		{id: 2}
	//		{id: 3}
	//		{id: 5}
	//		{id: 6}
	//		{id: 9}
	//		{id: 10}
```

根据数组中的对象的多个属性值排序，多条件排序；

```js
	var arr6 = [{id:10,age:2},{id:5,age:4},{id:6,age:10},{id:9,age:6},{id:2,age:8},{id:10,age:9}];
	arr6.sort(function(a,b){
		if(a.id === b.id){//如果id相同，按照age的降序
			return b.age - a.age
		}else{
			return a.id - b.id
		}
	})
	console.log(arr6);
	//输出新的排序
	//		{id: 2, age: 8}
	//		{id: 5, age: 4}
	//		{id: 6, age: 10}
	//		{id: 9, age: 6}
	//		{id: 10, age: 9}
	//		{id: 10, age: 2}
```

# Array方法 **ES5 + ES6**

## 	**ES5**

	1. Array.prototype.indexOf(value) : 得到值在数组中的第一个下标
	2. Array.prototype.lastIndexOf(value) : 得到值在数组中的最后一个下标
	3. Array.prototype.forEach(function(item, index){}) : 遍历数组
	4. Array.prototype.map(function(item, index){}) : 遍历数组返回一个新的数组，返回加工之后的值
			map() 方法返回一个新数组，数组中的元素为原始数组元素调用函数处理后的值。
		map() 方法按照原始数组元素顺序依次处理元素。
		注意： map() 不会对空数组进行检测。
		注意： map() 不会改变原始数组。
	
	5. Array.prototype.filter(function(item, index){}) : 遍历过滤出一个新的子数组， 返回条件为true的值


```js
	arr = [1,23];
	arr.forEach(function(item,index){
		console.log(item);
	})
	
	console.log(arr.map(function(item,index){
		return item * 2;
	}))	
```

```js
		console.log(arr.filter(function(item,index){
​			return item >= 2;
​		}))
```





## ES6 ECMA2015

```js
1. Array.from(v) : 将伪数组对象或可遍历对象转换为真数组
2. Array.of(v1, v2, v3) : 将一系列值转换成数组
3. find(function(value, index, arr){return true}) : 找出第一个满足条件返回true的元素
4. findIndex(function(value, index, arr){return true}) : 找出第一个满足条件返回true的元素下标

	var arr1 = '12345';
	console.log(Array.from(arr1));
	
	console.log(Array.of(1,2,3));

	console.log(new Array(1,2,3));   区别？
	
	console.log(arr.findIndex(function(item,index){
		return item > 10;
	}));

所有的方法都要注意三要素；
```

###  let

作用：同var一样来声明变量

变量提升：

全局变俩提升

会创建一个变量对象（scipt)用来手集全局作用域下let定义的变量，但是没有赋值

局部变量提升

会将var let定义的变量全部放到当前函数的变量对象中



**在块作用域内有效**，**不能重复声名**，**会预处理有变量提升但是不能提前使用提升的变量**

### const

常量不允许修改

### 解构赋值

根据key索取value

数组按照index索取

```js
let obj = {name:'kk',age:12,sex:'male'}

let name,age =obj2;

console.log(name,age)//kk,12
let arr = [4,423,32,324,421,32,1,2,3,4]
 function fun({name,age}){
        //利用函数的形参解构实参
        console.log(name,age)

    }
    fun(obj)
```

### 模板字符串

```js
let str1 = `我的名字叫${obj.name}我${obj.age}岁`;
```

### 简化对象写法

```js
let names = 'kobe';
let ages = 33
let obj3 = {
    //同名属性可以省略 key和value一样的时候
    ages,
    names,
    showName(){//省略函数等function:
        console.log(this.names);
    }
}
console.log(obj3)
obj3.showName();
```

### 箭头函数

1. 简洁

2. 箭头函数没有自己的this,箭头函数的this不是调用的时候决定的，而是在定义的时候处在的对象就是它的this

3. 扩展理解：箭头函数的this看外层的是否有函数

   如果有，外层函数的this就是内部箭头函数的this。

   如果没有，则this是window.

### 点点点运算符

第二次学习arguments用来收集实参的伪数组

不能直接去遍历对象只能遍历数组

```js
function fun(a,...values){
    //三点运算符必须放在最后
    console.log(arguments)
    // arguments.forEach()
    values.forEach(function (item,index){
        //item是值，index 是索引
        console.log(item,index);
    });
}
//第二次学习arguments用来收集实参的伪数组
fun(1,2,3,4);
```

### 形参默认值

```js
function fun3(ar = []){
    arr.forEach(function (item,index){
        console.log(item,index);
    })
}
```

### symbol

```js
let stmbol = Symbol('one')
console.log(stmbol);
let symbol = Symbol('two');
console.log(stmbol === symbol)
```

### Iterator 遍历器（迭代器）

for of -->**Symbol.iterator**

```js
    function iteratorUtil() {
           // iterator接口：方法||api
        console.log('迭代器执行');
        console.log(this)//window
        let index = 0;
        return {
            next: () => {
                // console.log(this)//window

                return index < this.length ? {value: this[index++], done: false} : {value: this[index++], done: true}
            }
        }
    }
 Array.prototype[Symbol.iterator] = iteratorUtil;
    for( let i of arr2){
        console.log(i)
     }
```

### class

1. 通过class定义类实现类的继承
2. 在类中通过constructor定义构造方法
3. 通过new来创建的实例
4. 通过extends来实现类的继承
5. 通过super调用父类的构造方法
6. 重写从父类中继承的一般方法

### 字符串扩展

includes(str)判断是否包含指定的字符串

startsWith(str)判断是否已制定字符串开头

endsWith(str)判断是否以指定字符串结尾

repeat（count)指定字符串重复次数

### 数值扩展

二进制与八进制表示方法：二进制0b八进制0o

Number.isFiniter(i)：判断是否是有限大的数

 判断是否有整数 NaN 直接去除小数 将字符串转换为相应数值 直接去除小数

### 数组扩展

Array.from(v) 将为数组或可遍历对象转化为真数组

Array.of(v1,v2,v3)将一系列值转化为数组

find(fun)找出第一个满足条件反返回true的元素

```js
let arr = [2,5,4,6,43,643,12];
let result = arr.find(function (item,index){
    if(item>=5){
        console.log(item);
        // return true;
    }
    
})
```

findindex(fun)找出第一个满足条件的返回true的元素下标

### 对象扩展

1 Object.is(1,2)判断两个数据是否完全相等

2 Object.assign(target,source1,source2..)

将对象的原属性复制到目标对象上

该操作会将后面的对象覆盖到前面对象

有两种叫法克隆 拷贝

```
3 直接操作_proto_属性
let obj2 = {};
obj2._proto_ = obj1;

```

### 容器

set map

set会自动去重

数组去重

```js
let uniqArr2 = arr =>[...new Set(arr)];
```



## ES7(16年)ECMA2016 

## object ES5

### object.create (protootype,[descriptors])

作用以指定对象的原型链创建新的对象

微信的对象制定新的属性，并对属性进行描述

value；指定值

writeable : 标识当前属性值是否可以修改默认为false

configurable  标识当前属性是否可以被删除 , 默认为 false

enumerable  标识当前属性是否能用 for in 枚举 默认为 false





null 和对象typeof的值都是object







# 正则表达式

正则表达式是一种字符串匹配规则

## 规则写法

### 修饰符

​		修饰符用于执行区分大小写和全局匹配:
​		i:忽略大小写
​		g: 执行全局匹配（查找所有匹配而非在找到第一个匹配后停止）。
​		m:执行多行匹配
​	

### 方括号

​		方括号用于查找某个范围内的字符：
​		

```
		[abc]    查找abc任意一个
		[^abc]   查找不是abc的任意一个
		[0-9]    查找任意一个数字    \d
		[a-z]    查找任意一个小写字母
		[A-Z]   查找任意一个大写字母
```

### 元字符

​	

```
	    .  匹配任意字符不包含\n（换行和结束符）
		\d  任意数字  等价于[0-9]
		\D  任意非数字  等价于[^0-9]
		\w  任意单词字符 数字 字母  下划线  [a-z A-Z 0-9 _]
		\W  任意非单词字符 [^a-z A-Z 0-9 _]
		\s   任意空白字符
		\S   任意非空白字符
		\b   单词边界
		\B   非单词边界
		\n   换行符
		\f   换页符
		\r   回车符
		\t   制表符
		\v   垂直制表符
```

### 量词

```
		+   1个或者多个前一个字符   \d+
		*   0个或者多个前一个字符   \d*
		？  0个或者1个前一个字符 \d?
		{n}  n个前一个字符      \d{2}     (\d{11})\1;
		{m,n} m到n个前一个字符  \d{2,4}
		{m,} 至少m个前一 个字符   \d{2,}
		$   结       ^\d{11}$
		^   开头
```

### 分组

```
		（）分组后的反向引用
		 | 
```

## 贪婪和非贪婪

​		量词后面的？代表非贪婪

## 正则对象的方法：

### 		Reg.test() 

​			test() 方法用于检测一个字符串是否匹配某个模式，如果字符串中含有匹配的文本，则返回 true，否则返回 false。

### Reg.exec()

​			exec() 方法用于检索字符串中的正则表达式的匹配。
​			该函数返回一个数组，其中存放匹配的结果。如果未找到匹配，则返回值为 null。

**注意**：此方法每次只会返回一个结果，如果要找到所有的，需要循环去调用必须全局匹配修饰；

找到字符串当中符合正则的子串
			找到字符串当中所有符合正则的子串
	

## 字符串方法使用正则

### str.match()：

在字符串中搜索符合规则的内容，搜索成功就返回内容，格式为数组，失败就返回null。如果不加g，那么返回第一次符合的结果，加g返回所有结果的数组

​	找一个是详细进行展示  找多个只是在一个数组展示找到的内容子串



### 	str.search()：

在字符串搜索符合正则的内容，搜索到就返回出现的位置（从0开始，如果匹配的不只是一个字母，那只会返回第一个字母的位置）， 如果搜索失败就返回 -1 	只能返回第一次；



​	**注意**：上面两个方法类似正则的方法 test和exec

Reg.exec()和str.match()     
		当不使用全局匹配时，两者的匹配效果都是返回第一次匹配成功的结果：

reg.test（）和str.search（）  前者返回的是true或者false   后者返回到的是匹配到的子串位置或者-1；

### str.replace():

查找符合正则的字符串，就替换成对应的字符串。返回替换后的内容。
			这个方法象当于做了两件事     先查找匹配    然后再用新的串把匹配到的串替换掉	