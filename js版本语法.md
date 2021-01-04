# “use strict”

1. 变量声明必须写var，不写var报错
2. 禁止this指向window,如果构造函数忘记写new那么this不会影响全局
3. 禁止随意删除变量
4. 函数不能有重复的参数；

## let使用及特点

1. 块级作用域声明变量     
2. es6都是处于严格模式下的
3.  let定义的变量不会进行预解析
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

