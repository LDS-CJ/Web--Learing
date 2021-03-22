

#### CSS学习总结

- [1.CSS是什么](#anchor2)

- [2.CSS语法组成](#anchor)

- [3.CSS如何生效](#anchor3)

- [4.CSS常用属性总结](#anchor4)

  ------

  

##### <span id ="anchor2">1.CSS 是什么:</span>

**CSS**是级联样式表（Cascading Style Sheets）的缩写。HTML 用于撰写页面的内容，而 CSS 将决定这些内容该如何在屏幕上呈现。

网页的内容是由 HTML的元素构建的，这些元素如何呈现，涉及许多方面，如整个页面的布局，元素的位置、距离、颜色、大小、是否显示、是否浮动、透明度等等。

万维网联盟 W3C（World Wide Web Consortium）意识到这个问题，于1997年推出 CSS 1.0（当前最新的版本是 CSS3），正式推动了内容（HTML）和表现（CSS）的分离，人们开始可以把所有的布局和样式代码从 HTML 中移除放入到 CSS 中。

CSS 入门极其容易，但要完全掌握及合理的应用则比较困难。

------

##### <span id="anchor">2.CSS语法组成：</span>

一条CSS样式规则由两个主要的部分构成：选择器，以`{}`包裹的一条或多条声明:

![](image/2.jpg)

这条规则表明，页面中所有的一级标题都显示为蓝色，字体大小为12像数。
说明：

- 选择器是您需要改变样式的对象（上图的规则就一级标题生效）。
- 每条声明由一个属性和一个值组成。（无论是一条或多条声明，都需要用`{}`包裹，且声明用`;`分割）
- 属性（property）是您希望设置的样式属性（style attribute）。每个属性有一个值。属性和值被冒号分开。

###### 选择器

- id选择器

   通过id值取得对象 id值是唯一的 

   ```html
   <p id="sky">蓝色的天空</p>
   <p id="forest">绿色的森林</p>
   
   #sky{
     color: blue;
   }
   #forest{
     color: green;
   }
   ```

   

- class选择器

   通过class取得对象 class值可以是不唯一的

   ```html
   <p class="center">我会居中显示的</p>
   <p class="red">我是红色的</p>
   <p class="center large red">我又红又大还居中</p>
   <p class="red">我也可以是红的</p>
   
   .center{
     text-align: center; //文字居中
   }
   .large{
     font-size: 30px; //字体宽度
   }
   .red{
     color: red; //前景色颜色 字体颜色
   }
   ```

   

   ```
1.群组选择器  如：p, body, img, div{}
   
   ```

2.兄弟选择器  如：p + p { color:#f00; }

3.属性选择器  如： p[title] { color:#f00; }

   4.包含（后代）选择器  如：body ul li{}

   5.子元素选择器 如：div > p{}

   6.ID选择器  如：#myDiv{}

   7.类选择器  如：.class1{}

   8.伪元素选择器  如：E:first-line，E:before

   9.伪类选择器  如：E:first-child ，E:visited，E:focus，E:enabled

   10.标签选择器  如：p { font-size:1em; }
   ```
   
   ##### <span id ="anchor3">3.CSS如何生效:</span>
   
1. ###### 外部样式表
   
      新建如下内容的一个 HTML文件（后缀为.html)：
   
      ```html
      <!DOCTYPE html>
      <html>
      <head>
        <meta charset="utf-8">
        
          <!-- 注意下面这个语句，将导入外部的 mycss.css 样式表文件 -->
        <link rel="stylesheet" type="text/css" href="mycss.css">   ！！！
       
          <title>页面标题</title>
      </head>
   <body>
        <h1>我是有样式的</h1>
     <hr>
        <p class="haha">还是有点丑：)</p>
   </body>
   </html>
   ```

      ```css
      body {
        background-color: linen;
        text-align: center;
      }
      h1 {
        color: red;
      }
      .haha {
        margin-top: 100px;
        color: chocolate;
        font-size: 50px;
   }
      ```

   

   2. ###### 内部样式表
   
      我们也可以将样式放在 HTML 文件中，这称为内部样式表。如运用<style></style>将css部分代码写在html代码中：
   
      ```html
        <style>
          body {
            background-color: linen;
            text-align: center;
          }
          h1 {
            color: red;
          }
          .haha {
            margin-top: 100px;
            color: chocolate;
            font-size: 50px;
          }
       </style>
      ```
   
      小总结：样式的优先级问题，从高到低分别是：
      
      内联样式
      
      内部样式表或外部样式表
      
      浏览器缺省样式
      
      哪个样式定义离元素的距离近，哪个就生效。
      
      ------
      
      
      
      ##### <span id ="anchor4">4.CSS属性设置:</span>
      
      background-color 背景颜色
      
      color 前景色
      
      通过设置rgb颜色设置
      
      height 高度
      
      weight 宽度
      
      text-align 文本格式 left center right 左 中 又对齐
      
      ```html
        height: 100px;
        width: 500px;
        background-color: rgb(73, 138, 60);
        text-align: right;
        color: red;
      ```
      
      ###### 盒子模型：
      
      盒子模型指的是一个 HTML 元素可以看作一个盒子。从内到外，这个盒子是由**内容 content, 内边距 padding, 边框 border, 外边距 margin**构成的，如下图所示：
      
      ![](image/3.jpg)
      
      **说明：**
      
      - Content 盒子的内容，如文本、图片等
      
      - Padding 填充，也叫内边距，即内容和边框之间的区域
      
      - Border 边框，默认不显示
      
      - Margin 外边距，边框以外与其它元素的区域
      
        

补充：默认情况下 Margin Border Padding content 边距为0  因此 4条线重合

![border](image/4.jpg)

留意上图，你会发现一个元素真正占据的宽度应该是：
左外边距 + 左边框宽度 + 左内边距 + 内容宽度 + 右内边距 + 右边框宽度 + 右外边距

```css
  border: 10px solid blue;
  padding: 25px;
  margin: 25px;
  padding: 20px; 
  padding-top: 20px;
  padding-bottom: 100px;
  padding-right: 50px;
  padding-left: 80px;
  padding: 25px 50px 75px 100px; 
  padding: 25px 10px; 
```

###### 定位属性:

position 属性用于对元素进行定位。该属性有以下一些值：

- static 静态  设置为静态定位`position: static;`，这是元素的默认定位方式，
- relative 相对  设置为相对定位`position: relative;`，这将把元素相对于他的静态（正常）位置进行偏移
- fixed 固定  设置为固定定位`position: fixed;`，这将使得元素固定不动（即使你上下左右拖动浏览器的滚动条）
- absolute 绝对  设置为绝对定位`position: absolute;`，将使元素相对于其**最近设置了定位属性（非static）的父元素**进行偏移。
  如果该元素的所有父元素都没有设置定位属性，那么就相对于`<body>`这个父元素。

设置了元素的`position`属性后，我们才能使用`top, bottom, left, right`属性，否则定位无效。

###### 不透明度设置：

我们可以用`opacity`对任何元素（不过常用于图片）设置不透明度。
值在`[0.0～`1.0]之间，值越低，透明度越高。

###### 组合选择器：

1.后代选择器

以空格作为分隔，如：`.haha p` 代表在`div`元素内有`.haha`这种类的所有元素。

2.子选择器

也称为直接后代选择器，以`>`作为分隔，如：`.haha > p` 代表在有`.haha`类的元素内的直接`<p>`元素。

######  伪类和伪元素：

伪类（pseudo-class）或伪元素（pseudo-element）用于定义元素的某种特定的状态或位置等。
比如我们可能有这样的需求：

- 鼠标移到某元素上变换背景颜色

- 超链接访问前后访问后样式不同

- 离开必须填写的输入框时出现红色的外框进行警示

- 保证段落的第一行加粗，其它正常

  ```css
  /* 选择器后使用 : 号，再跟上某个伪类/伪元素 */
  selector:pseudo-class/pseudo-element {
    property:value;
  }
  ```

  伪类选择符
  
  ![](image/5.jpg) 
  
  伪元素选择符：
  

![](image/1.jpg)

