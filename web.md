# 前端之路



无论是前端工程师还是后台工程师，我们的工作内容都是开发软件。

## 软件的分类：



## C/S架构的软件

1. C表示客户端，S表示服务器
   用户通过客户端来使用软件□ 服务器用来处理软件的业务逻辑

    客户端：QQ、office、360、王者荣耀 …

   **特点**

   1、C/S架构软件必须要安装后才可以使用

2. C/S架构软件软件更新时，服务器和客户端都需要更

3. C/S架构的软件无法跨平台使用

4. C/S架构的软件客户端和服务器间的通信采用自有的协议，安全性较 好 



## B/S

B表示浏览器，S同样表示服务器

B/S本质上也是C/S，只不过B/S使用浏览器作为软件的客户端

B/S实际上就是一个一个的网站，我们可以通过访问一个网站来使用软件
**京东、淘宝、12306**□ 例子：
1、不需要安装可以直接使用□ 2、软件更新客户端无需更新□ 3、软件可以跨平台使用□ 4、B/S架构的软件，客户端和服务器间的通信采用的公共的HTTP协议， 安全性较差：

## Html

1. 根据w3c的规范，一个网页有三部分构成、表现、行为三者分离，分别对应三种语言 结构**html**表现**css****行为**javascript**

2. 耦合，代码之间的关系过于紧密，修改一个必须要同时修改西塔代码

3. 解耦

4. 基本语法

   标签、成对出现 自行结束标签 属性 常用p段落 br换行 hr水平线

   实体 &实体名字

   `&nbsp; 空格□ □ &lt; 小于号 □ &gt; 大于号 □ &copy; 版权符号 □ &#Unicode; 编码表`

   

## 常用标签

meta标签，表示网页中的一些元数据
name：要设置的数据的名字 content：要设置的数据的值 http-equiv：设置Http协议的响应头 属性：
`1.设置网页的描述信息    1 <meta name="description" content="这是一个非常非常好的网站...">`
`2.设置网页的关键字    1 <meta name="keywords" content="HTML5,Java,大数据">`
`3.设置网页的重定向    1 <meta http-equiv="refresh" content="3;url=https://www.baidu.com">`

## 语义化标签

1. header 表示网页的头部，头部可以包含logo导航搜索框 **广告条**
2. main表示网页的 主题一个网页只有一个
3. footer 表示网页的底部可以包含版权声明
4. nav表示导航
5. article 表示网页中的内容
6. aside侧边栏
7. section 表示一个区块
8. hgroup表示一个标题组
9. div表示一个区块

以上都是表示一个区块块元素会在页面中独占一行

## .**语义化标签**

em 强调（语气）

 strong 强调重要性

 i 斜体 

b 加粗

 q 短引用 以上这些元素都是行内元素（内联元素），在页面中不会独占一行

以上这些元素都是行内元素（内联元素），在页面中不会独占一行 blockquote 长引用

外部资源标签

图片标签

```html
<img src="" alt="图片" width height>
```

## 相对路径

相对路径是相对与当前文件所在的目录计算的

**./**表示当前目录（可以省略）

**../**表示上一级目录返回几级就写几个

```pdf
   root        
   - index.html  1.jpg     
   - 1.jpg              
   root    
   - index.html  hello/1.jpg  
   - hello       
     - 1.jpg     
   root        
   - index.html  hello/abc/1.jpg       
   - hello        
    - abc       
     - 1.jpg                  
   root    
   - 1.jpg       
   - hello         
    - index.html   ../1.jpg                    
   root    
   - 1.jpg      
   - hello   
    - abc   
     - index.html ../../1.jpg 
```

## 内联框架

**iframe**用来引入一个外部网页

```html
<iframe src="https://www.baidu.com" frameborder="0" width="500" height="500"> </iframe>

```

### 音频视频标签

使用audio标签来引入音频文件

使用video标签来引入视频文件

controls autoplay loop

### 超链接

href 跳转的目标的路径

```
□ <a href="https://www.baidu.com">link</a> - 打开外部的页面
□ <a href='../hello.html'>link</a> - 打开内部的页面
□ <a href='#id属性值'>link</a> - 跳转页面的指定位置（锚点）
```

- target 打开页面的位置

_self 默认值 当前窗口打开 

_blank 在新窗口打开（慎用）

## 列表

```pdf
1 <ul>    2    <li></li>    3    <li></li>    4 </ul> - 无序列表
1 <ol>    2    <li></li>    3    <li></li>    4 </ol> - 有序列表
1 <dl>    2    <dt></dt>    3    <dd></dd>    4 </dl> - 定义列表
```
## css

 层叠样式表 - CSS用于设置页面中元素的样式，属于结构表现行为中的表现。
  可将css代码编写到标签的style属性中      1 <p style="color: skyblue;font-size: 60px;">今天天气真不错</p> ○ 第一种，内联样式
  可以将css代码编写到一个style标签中    1   

```css
    <style>    2                p{    3                        color:greenyellow;    4                        font-size: 50px;    5                        background-color: yellow;    6                }    7                    8                h1{    9                        color: yellowgreen   10                }   11        </style>
```

 第二种，内部样式表○
  可以将css代码编写到一个外部文件中，然后通过link标签引入      1 <link rel="stylesheet" href="style.css"> 

第三种

<link rel ="stylesheel" href='""'>

## CSS基本的语法

###  选择器 声明块

  通过选择器可以选中页面中的指定元素
□ 语法：标签名（p{} div{} span{}）   元素选择器
□ 语法：#id (#box{} #p1{} #wrap{})   id选择器
□ 语法：.class(.box{} .p1{} .wrap{} .outer{})   类选择器
□ 语法：选择器1,选择器2,…选择器N   选择器分组（并集选择器）
□ 语法：*   通配选择器
□ 语法：选择器1选择器2…选择器N   交集选择器
□ 语法：祖先 后代 （div span{}  p em{}）   后代元素选择器
□ 语法：父元素 > 子元素 （div > span{}  p > em{}）   子元素选择器
□ 语法：兄 + 弟   下一个兄弟元素
□ 语法：兄 ~ 弟   后边所有兄弟元素

## 伪元素选择器

□ **伪类都是以 : 开头的**
 :first-child 第一个子元素 

 :first-of-type 同类型的第一个子元素 

 :last-child 最后一个子元素 

 :last-of-type 同类型的最后一个子元素 

 :nth-child(n) 第N个子元素

  :nth-of-type(n) 同类型的第N个子元素 

 :only-child 唯一的子元素

  :only-of-type 同类型中唯一的子元素 

 :empty 空元素 

 :not() 除了

  :link 正常的链接（没访问过的链接） 

 :visited 访问过的链接 

 :hover 鼠标移入的状态 

 :active 鼠标点击的状态 

□ 伪类表示元素一些特殊状态或位置


## CSS特点

**继承**

就像后代会继承祖先的财产一样，后代元素一会继承到祖先元素的样式○ 继承的存在大大的简化了我们的开发，利用可以在一个祖先元素上设置一些公共的 样式，这样其所有的后代元素都会同时具有该样式。 ○ 但是并不是所有的样式都会被继承，像背景、border、width、height 

## **选择器的权重**

当使用不同的选择器选中同一个元素，并且为它的同一个样式设置不同的值，这时 就发生了样式冲突。
○
内联样式（1, 0, 0, 0）

  id选择器（0, 1, 0 , 0）

  类和伪类（0, 0, 1, 0）

  元素选择器（0, 0, 0, 1）

  通配选择器（0,0,0,0）

  继承的样式，没有优先级

  发生样式冲突时，哪个样式会生效由选择器的优先级决定：

○ 优先级在计算时，需要将所有用到的选择器进行相加，然后再比较，优先级高的优 先使用，如果优先级一样则使用靠后的样式。

!important 可以在一个样式的最后添加它，这样该样式将会获得最高的优先级，优 先所有样式显示，慎用

## 单位

像素就是屏幕上一个一个的小点□ 像素分成两种：CSS像素和物理像素□ 我们在编写网页时使用的是CSS像素，在PC端默认情况下（没有缩 放），1css像素=  1物理像素 □ 如果对pc端进行放大，或者在移动端开发，则1个css像素会对应多个物 理像素 □ 像素（px） 
百分比会根据父元素的指定的值来计算当前元素的值□ 一般我们在一些响应式的开发中会使用到百分比□
默认情况下包含块就是离当前元素最近的块级祖先元素 包含块□
百分比（%） 
长度单位○

**颜色单位○**

□ 颜色名

red orange yellow blue green black …

**□RGB值▪**

使用红绿蓝三种颜色的光的浓度来调配出不同的颜色

 rgb(红色, 绿色, 蓝色)取值范围 0-255 / 0% - 100%

 rgba（）

**a（alpha）表示不透明度，范围是0-1**

**□ 十六进制rgb值**

语法：#红色绿色蓝色

□ **范围 00 - ff**

□ 例子：#ff0000  --> #f00



**工业中设置颜色的方式**

HSL值

H 色相 （0-360） 他通过三个值来设置颜色□

S 饱和度 （0% - 100%） L 亮度 （0% - 100%

## 盒子模型

 在CSS中将每一个元素都设置成了一个矩形的盒子
▪ 内容区相当于盒子的内部空间，所有的子元素都在父元素的内容区中存在 

▪ 使用width和height来设置内容区的宽度和高度 ○ 内容区
▪ 内容区和边框间的距离称为内边距
○ 内边距
▪ 边框是盒子可见框的边界，出了边框就不在属于盒子的可见框 ▪ 可见框的大小，由内容区、内边距和边框共同决定

○ 边框
外边距不会影响盒子可见框的大小，但是会影响到盒子的位置 ○ 外边距（margin）

- 每一个盒子从内到外有以下几个部分组成
- **子元素在父元素中，水平方向的值必须要满足如下的等式：**○ -

**margin-left + border-left + padding-left +width + padding-right + border-right + margin-right = 父元素的width属性** 

▪ 如果不满足等式，默认情况下会自动调整设置为auto的属性值，以使等式满 足，如果所有的值都不是auto，则调整右外边距以满足等式
□ margin : 0 auto;
▪ 如果将左右外边距同时设置为auto，宽度固定，则子元素会自动在父元素中 水平居中
![image-20201108163744185](C:\Users\30278\AppData\Roaming\Typora\typora-user-images\image-20201108163744185.png)

盒子模型



# 待更新

## 第二次更新

盒子模型的几个相关属性

**overflow**

设置如何处理溢出内容

可选值：

1. visible默认值不会处理溢出的内容在盒子外部显示
2. hidden溢出的内容会被裁剪不在页面中显示
3. scroll生成水平和垂直防线大哥滚动条
4. auto更据需求生成滚动条

**display**

设置元素的框的类型
▪ block 元素作为块元素显示

 ▪ inline 元素作为行内元素显示

 ▪ inline-block 元素作为行内块元素显示

 ▪ none 元素不在页面中显示 

▪ table 元素会作为一个表格显示 

▪ flex 元素会作为一个弹性容器显示 

▪ inline-flex 元素会作为行内弹性容器显示 

○ 可选值：

- visible 默认值，元素正常显示 
- ▪ hidden 元素在页面中隐藏（依然占据页面的位置）

文档流

文档document 网页

###   块元素在文档流中的特点：

在页面中自上向下排列

 ▪ 默认跨度是父元素的全部

 ▪ 默认高度被内容撑开 



###  行内元素在文档流中的特点：

▪ 在页面中自左向右顺序排列，一行占满换到第二行继续自左向右

 ▪ 默认宽度和高度都是被内容撑开

### 行内元素的盒子模型

行内元素不支持设置宽度和高度

行内元素支持水平方向的内边距边框外边距

​		▪可以设置垂直方向的内边距、边框、外边距，但是不会影响布



### BFC**坍塌**

解决办法：（块级格式化环境BFC block format context）一旦开启bfc他将开启一个独立的区域

1. 开启bfc的元素子元素垂直边距不会传递给父元素
2. 不会被浮动元素所覆盖
3. 可以包含浮动元素

BFC开启：

1. 浮动
2. 将元素设置成行内块 inline-block
3. 将元素overflow：auto;hidden;

clear:left清除左侧浮动 both

::after伪元素放置div最后

```css
.clearfix::after{

content:";

display:block;

clera:both;}

外边距重叠
.name::before{
    content:"";
        display:table;
}
```

## 1.定位（position）

 定位是CSS中一种高级的布局手段，通过定位可以将元素摆放到页面的任意位置。

○ static 默认值，元素是静止的，没有开启定位 

○ relative 开启元素的相对定位 

○ absolute 开启元素的绝对定位 

○ fixed 开启元素的固定定位 - position的可选值：

###  **- 相对定位**

○ 开启了相对定位的元素，如果不设置偏移量元素不会发生任何变化 

○ 相对定位的元素不会脱离文档流 

○ 相对定位不会改变元素的性质 

○ 相对定位的元素会提升一个层级 

○ 相对定位的元素是相对于自身在文档流中的位置进行定位的

### **绝对定位**

○ 开启了绝对定位的元素，如果不设置偏移量元素的位置不会发生任何变化 ‘

○ 绝对定位会使元素脱离文档流 

○ 绝对定位会改变元素的性质，行内元素变成块元素，块元素宽高被内容撑开

 ○ 绝对定位会使元素提升一个层级

 ▪ 初始包含块：

□ html（根元素）

 ▪ 包含块：

□ 默认情况下包含块就是离当前元素最近的块级祖先元素

 □ 对于绝对定位元素来说，包含块是离它最近的开启了定位的祖先元素， 如果所有的祖先元素都没有开启定位，则其包含块就是初始包含块。

○ 绝对定位元素相对其包含块进行定位

### **固定定位**

固定定位的大部分特点和绝对定位一样，不同点是固定定位是相对于视口进行定位 的，并且固定定位元素会固定在网页的视口上，不会随网页滚动。

### 元素的层级

○ 我们可以通过z-index来设置定位元素的层级

 ○ 它需要一个整数作为参数，值越大层级越高，层级越高越优先显示，层级一样优先 显示后边的，

 ○ **祖先元素的层级再高也不会盖住后代元素**

○ 我们可以通过z-index来设置定位元素的层级。 ○ 它需要一个整数作为参数，值越大层级越高，层级越高越优先显示，层级一样优先 显示后边的， ○ 祖先元素的层级再高也不会盖住后代元素

## 过度

transition

1. 设置过渡效果

2. 可以同时设置过度的所有效果

3. 过度属性

   transition -durarion

4. 过度的延时

   transition-delay

   过度的时间函数

   transition-timing-function

## 动画

关键帧关键帧用来指定动画的每一步执行的位置

**创建关键帧**

@keyframes名字{

from{}

50%{}

to{}

}

### **动画的属性**

**动画的名字**

animation-name

**动画持续的时间**

animation-duration

**动画的延时**

animation-delay

动画播放的状态

animation-play-state

### 变形

transform

可以用来设定元素的位置角度的大小的改变

translateX() translateY() translateZ()

位移函数

rotateX() rotateY()rotataZ()

旋转的函数



## 渐变

css中可以通过背景来设置渐变效果

关于渐变的注意事项渐变的是图片不是颜色

我们需要通过background或者background的简写属性来设置渐变效果

### 线性渐变

linear-gradient(角度，颜色 位置，颜色 位置，颜色 位置)

例子：

background-image：linear-gradient(red,orange,yellow)

![image-20201111194813481](C:\Users\30278\AppData\Roaming\Typora\typora-user-images\image-20201111194813481.png)

background-image:;inear-gradinet(toright,red,orange,yellow);

![image-20201111194821966](C:\Users\30278\AppData\Roaming\Typora\typora-user-images\image-20201111194821966.png)

### 径向渐变

radial-gradient(形状at位置 ，颜色颜色颜色)

background-image:radial-gradinet(green,yellow,orange)

![image-20201111195102519](C:\Users\30278\AppData\Roaming\Typora\typora-user-images\image-20201111195102519.png

![image-20201111195227528](C:\Users\30278\AppData\Roaming\Typora\typora-user-images\image-20201111195227528.png)