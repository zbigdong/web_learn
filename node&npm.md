# npm

## 永久使用npm

```
打开cmd使用命令：npm config set registry https://registry.npm.taobao.org// 配置后可通过下面命令来验证是否成功
　npm config ls
// 此时：metrics-registry = "http://registry.npm.taobao.org/"表示设置成功npm config get registry// 或npm info express
```

## 通过cnpm

```
npm install -g cnpm --registry=https://registry.npm.taobao.org
// 使用
cnpm install expresstall express
```

# less

css预处理语言他扩展了css语言maxmin、函数等特性

使用方法

1. 打开环境变量窗口
2. 找到npm path路径 C:\Users\30278\AppData\Roaming\npm

​    cnpm install less

## less简单使用

```
//@import "style";
//把外部的less代码放入到当前less中

.box1{
  width: 100 + 500px;
  //可以使用加减乘除
  height: 100px;
  background-color: red;
  .box2{
    width: @a;
    height: $width;
    background-color: aqua;
  }
}
@a:88px;
//使用@符来定义变量
@w:100px;
@c:#f10000;
//驼峰命名法,变量名首字母小写其余字母小写
@className:box2;
//使用.@{className}{}
//使用变量时候就近原则
body{
  background-color: darken(blue,100%);
//  用于颜色加深
}
.box4{
  @a:w;
  width:@@a;
  //每一个{都是一个独立的作用域
  //我们使用变量时会在当前的{中寻找,如果找到会直接使用
  //如果么有就去上一级寻找知道找到到位置如果摘不到就报错
}
//mixins通过mixins可以将不同的样式进行混合使用
//.box5{
//  .box4()
//}
//extend()可以将其他选择器上的样式扩展到当前选择器上
//和mixins不同的是 一个全部复制
//extend(是通过选择器分组的样式来对样式进行扩展
//继承2的所有的样式
.box5:extend(.box1 all){}

.hello(@a){
  width:@a;
  height: $width;
  background-color: aquamarine;
}
//&表示外层选择器
ul{
  background-color: antiquewhite;
  &>li{
    float: left;
  }
}
```

# CSS里面的变量:

html{--name:values;}

# 弹性盒子

display inline-flex和flex两种

要先设置弹性容器；

flex 简写三个属性值

flex: flex-grow flex-shrink flex-basis控制增长 缩减 默认长度；

```
/*
    每一个元素缩减多少，有元素的 flex-basis flex-shrink 共同决定
        溢出的大小（200）
        ----------------------------
        第一个元素 flex-basis *  flex-shrink +  第二个元素 flex-basis *  flex-shrink

        200 除以 400 = 0.5

        第一个元素缩减 = flex-shrink * 0.5 * flex-basis
        第一个元素缩减 = flex-shrink * 0.5 * flex-basis



*/
```

## 设置方向

flex-direction:**column; row;**

row-reverse(自右向左)

column 主轴自上到下；同理；

flex-wrap:wrap;设置换行

flex-flow: column wrap;

flex-shrink:0;缩小；

## 设置间距对齐方式

justify-content:space between;将空白区域平均分配到弹性元素之间；

around将空白空间设置到袁术的前后

space-evenly将空白元素设置到元素的一侧；

stretch；拉伸使元素充满盒子



**align-items设置对齐方式**



# 视图

