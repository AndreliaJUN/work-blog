## flex布局详解

### 1.flex布局的优势

- 传统布局：兼容性好，布局繁琐，局限性在移动端不能很好布局 
- Flex布局：简单，操作方便，兼容性差 
- Pc采用传统布局，移动端或者不考虑兼容的pc可采用flex布局

### 2.flex布局原理

- Flex布局原理就是：给父盒子添加flex属性，来控制子盒子的位置排 列方式从而实现flex布局 
- 当我们为父盒子设为 flex 布局以后，子元素的 float、clear （指定段落的左侧或右侧不允许浮动的元素：clear:both）和 vertical-align（设置一个元素的垂直对齐方式） 属性将失效。 
- Flex布局又叫伸缩布局、弹性布局、伸缩盒布局、弹性盒布局、flex 布局

### 3.flex布局常用属性

#### 容器的属性

##### a.justify-content

**通过justify-content能够设置主轴子元素排列形式** 

- 值为flex-start 所有子元素在主轴头部显示 
- 值为flex-end 所有子元素在主轴尾部显示 
- 值为center 所有子元素**在主轴居中对齐** 
- 值为space-around 所有**子元素平分剩余空间** 
- 值为space-between 所有子元素**先两边贴边在平分剩余空间**

```html
<div class="parent">
     <p class="child"></p>
     <p class="child"></p>
     <p class="child"></p>
  </div>
```



```css
.parent{
       width: 100%;
       height: 300px;
       background-color: pink;
       display: flex;
       justify-content:space-around;
    }
    .child{
      width: 10%;
      height: 200px;
      background-color: #323232;
    }
```

![](D:/typora笔记/工作遇到的问题/img/2021-09-01_092805.png)

```
.parent{
       width: 100%;
       height: 300px;
       background-color: pink;
       display: flex;
       justify-content:space-between;
    }
    .child{
      width: 10%;
      height: 200px;
      background-color: #323232;
    }
```



![](D:/typora笔记/工作遇到的问题/img/2021-09-01_092950.png)

```
  .parent{
       width: 100%;
       height: 300px;
       background-color: pink;
       display: flex;
       justify-content:center;
    }
    .child{
      width: 10%;
      height: 200px;
      margin-right: 30px;
      background-color: #323232;
    }
```

![](D:/typora笔记/工作遇到的问题/img/2021-09-01_092222.png)

```
.parent{
       width: 100%;
       height: 300px;
       background-color: pink;
       display: flex;
       justify-content:flex-start;
    }
    .child{
      width: 10%;
      height: 200px;
      margin-right: 30px;
      background-color: #323232;
    }
```

![](D:/typora笔记/工作遇到的问题/img/2021-09-01_092304.png)



```css
   .parent{
       width: 100%;
       height: 300px;
       background-color: pink;
       display: flex;
       justify-content:flex-end;
    }
    .child{
      width: 10%;
      height: 200px;
      margin-right: 30px;
      background-color: #323232;
    }
```



![image-20210914161857331](D:/typora笔记/工作遇到的问题/img/image-20210914161857331.png)

##### b.flex-direction

**Flex布局中默认的主轴是row，x轴  主轴为水平方向，起点在左端。如果想改变主轴方向可通过设置flex-direction来改变** 

- flex-direction:column;将主轴改为y轴，纵轴  
- flex-direction:row; 将主轴改为x轴，横轴 
- flex-direction:row- reverse;主轴为x轴，并且翻转  主轴为水平方向，起点在右端。
- flex-direction:column- reverse;主轴为y轴，并且翻转

```
.parent{
      width: 800px;
      height: 1000px;
      margin: 0 auto;
       background-color: pink;
       display: flex;
       flex-direction: column;
       justify-content:space-between;
    }
    .child{
      margin: 0;
      width: 100px;
      height: 200px;
      background-color: #323232;
    }
```

<img src="D:/typora笔记/工作遇到的问题/img/image-20210906100703326.png" style="zoom:67%;" />



```
.parent{
      width: 800px;
      height: 1000px;
      margin: 0 auto;
       background-color: pink;
       display: flex;
       flex-direction: row;
       justify-content:space-between;
    }
    .child{
      margin: 0;
      width: 100px;
      height: 200px;
      color: blanchedalmond;
      background-color: #323232;
    }
```



![](D:/typora笔记/工作遇到的问题/img/image-20210906100621871.png)

```
    .parent{
      width: 800px;
      height: 1000px;
      margin: 0 auto;
       background-color: pink;
       display: flex;
       flex-direction: row-reverse;
       justify-content:space-between;
    }
    .child{
      margin: 0;
      width: 100px;
      height: 200px;
      color: blanchedalmond;
      background-color: #323232;
    }
```



![](D:/typora笔记/工作遇到的问题/img/image-20210906100922615.png)

```
    .parent{
      width: 800px;
      height: 1000px;
      margin: 0 auto;
       background-color: pink;
       display: flex;
       flex-direction: column-reverse;
       justify-content:space-between;
    }
    .child{
      margin: 0;
      width: 100px;
      height: 200px;
      color: blanchedalmond;
      background-color: #323232;
    }
```



<img src="D:/typora笔记/工作遇到的问题/img/image-20210906101009444.png" style="zoom: 67%;" />


![](D:/typora笔记/工作遇到的问题/img/image-20210906101650878.png)

##### c.flex-wrap

- 开启flex布局后默认为不换行 （如果子盒子比较多总宽度超过了父盒子那么在不换行的情况下所有的盒子将被压缩宽度减小放到父盒子里面）
- 如果想要换行效果设置flex-wrap：wrap `wrap`：换行，第一行在上方。
- `wrap-reverse`：换行，第一行在下方。

```
    .parent{
      width: 1000px;
      margin: 0 auto;
       background-color: pink;
       display: flex;
       flex-wrap: wrap;
    }
    .child{
      margin: 0;
      width: 200px;
      height: 200px;
      color: blanchedalmond;
      background-color: #323232;
    }
```



![image-20211129095215375](D:\typora笔记\工作遇到的问题\img\image-20211129095215375.png)

```
    .parent{
      width: 1000px;
       height: 400px;
       margin: 0 auto;
       background-color: pink;
       display: flex;
       flex-wrap: nowrap;
    }
    .child{
      margin: 0;
      width: 200px;
      height: 200px;
      color: blanchedalmond;
      background-color: #323232;
    }
```

![image-20211129095303945](D:\typora笔记\工作遇到的问题\img\image-20211129095303945.png)

```
    .parent{
      width: 1000px;
      margin: 0 auto;
       background-color: pink;
       display: flex;
       flex-wrap: wrap-reverse;
    }
    .child{
      margin: 0;
      width: 200px;
      height: 200px;
      color: blanchedalmond;
      background-color: #323232;
    }
```



![image-20211129095349663](D:\typora笔记\工作遇到的问题\img\image-20211129095349663.png)


##### d.align-items

**align-items属性定义项目在交叉轴上如何对齐（设置在侧轴上的子元素排列方式,子元素是单行时才能设置）。**

> ```css
> .box {
> align-items: flex-start （从上到下）| flex-end （从下到上） | center （挤在一起居中）| baseline | stretch（拉伸）;
> }
> ```

```
    .parent{
      width: 1000px;
      height: 400px;
      margin: 0 auto;
       background-color: pink;
       display: flex;
       /*当侧轴为y轴时在垂直方向上居中*/
       align-items:center
    }
    .child{
      margin: 0;
      width: 200px;
      height: 200px;
      margin-right: 10px;
      color: blanchedalmond;
      background-color: #323232;
    }
```

![](D:/typora笔记/工作遇到的问题/img/image-20210906105428079.png)

```
.parent{
      width: 1000px;
      height: 400px;
      margin: 0 auto;
       background-color: pink;
       display: flex;
       align-items:flex-end
    }
    .child{
      margin: 0;
      width: 200px;
      height: 200px;
      margin-right: 10px;
      color: blanchedalmond;
      background-color: #323232;
    }
```



![](D:/typora笔记/工作遇到的问题/img/image-20210906105726118.png)

```
 .parent{
      width: 1000px;
      height: 400px;
      margin: 0 auto;
       background-color: pink;
       display: flex;
       align-items:flex-start
    }
    .child{
      margin: 0;
      width: 200px;
      height: 200px;
      margin-right: 10px;
      color: blanchedalmond;
      background-color: #323232;
    }
```

![](D:/typora笔记/工作遇到的问题/img/image-20210906105825759.png)

```
   .parent{
       width: 100%;
       height: 500px;
       background-color: pink;
       display: flex;
       align-items: stretch;
    }
    .child{
      width: 10%;
      /* 子盒子不要设置高度 */
      /* height: 200px; */
      margin-right: 30px;
      background-color: #323232;
    }
```

![image-20210914162206131](D:/typora笔记/工作遇到的问题/img/image-20210914162206131.png)

既居中对齐又水平对齐

```css
.parent{
       width: 100%;
       height: 500px;
       background-color: pink;
       display: flex;
       align-items: center;
       justify-content: center;
    }
    .child{
      width: 10%;
      height: 200px;
      margin-right: 30px;
      background-color: #323232;
    }
```



![image-20210914162956848](D:/typora笔记/工作遇到的问题/img/image-20210914162956848.png)

##### e.align-content

align-content设置侧轴上的子元素的排列方式（只能用于子项出现换行的情况（多行），在单行下是没有效果的。）

- flex-start 默认值在侧轴的头部开始排列
- flex-end 在侧轴的尾部开始排列
- center在侧轴中间显示
- space-around子项在侧轴平分剩余空间
- space-between子项在侧轴先分布在两头，再平分剩余空间
- stretch设置子项元素高度平分父元素高度

***只设置换行不设置align-content的时候***

```html
  <style>
   .parent{
       width: 800px;
       height: 800px;
       background-color: pink;
       display: flex;
       flex-wrap: wrap;
    }
    .child{
      width: 150px;
      height: 150px;
      margin-right: 30px;
      background-color: #323232;
    }
  </style>

<body>
  <div class="parent">
    <p class="child">子盒子1</p>
    <p class="child">子盒子2</p>
    <p class="child">子盒子3</p>
    <p class="child">子盒子4</p>
    <p class="child">子盒子5</p>
    <p class="child">子盒子6</p>
    <p class="child">子盒子7</p>
    <p class="child">子盒子8</p>
  </div>
```

<img src="D:/typora笔记/工作遇到的问题/img/image-20210914164441832.png" alt="image-20210914164441832" style="zoom:50%;" />

**设置为center**

<img src="D:/typora笔记/工作遇到的问题/img/image-20210914164557711.png" alt="image-20210914164557711" style="zoom:50%;" />

**space-around**

<img src="D:/typora笔记/工作遇到的问题/img/image-20210914164728964.png" alt="image-20210914164728964" style="zoom:50%;" />

**space-between**

<img src="D:/typora笔记/工作遇到的问题/img/image-20210914164833447.png" alt="image-20210914164833447" style="zoom:50%;" />

**设置为flex-end**

<img src="D:/typora笔记/工作遇到的问题/img/image-20210914164931110.png" alt="image-20210914164931110" style="zoom:50%;" />

##### f.flex-flow

flex-flow属性是flex-direction和flex-wrap属性的复合属性

`flex-flow:row wrap`

#### 项目的属性

##### a.flex

flex设置子项目占的份数

**两边定宽中间自适应布局**

```html
  section {
    width: 60%;
    height: 150px;
    background-color: pink;
    margin: 0 auto;
    display: flex;
  }
  section div:nth-child(1){
    width: 100px;
    height: 150px;
    background-color: rgb(87, 67, 67);
  }
  section div:nth-child(2){
    flex: 1;
    background-color: rgb(148, 86, 86);
  }
  section div:nth-child(3){
    width: 100px;
    height: 150px;
    background-color: rgb(59, 57, 57);
  }

  <section>
    <div></div>
    <div></div>
    <div></div>
  </section>
```



![image-20210914181549421](D:/typora笔记/工作遇到的问题/img/image-20210914181549421.png)

**等分布局**

```css
  p {
    width: 60%;
    height: 150px;
    background-color: pink;
    margin: 100px auto;
    display: flex;
  }
  p span{
     flex: 1;
  }
  <p>
    <span>1</span><span>2</span><span>3</span>
  </p>
```

![image-20210914185729086](D:/typora笔记/工作遇到的问题/img/image-20210914185729086.png)

```css
  p {
    width: 60%;
    height: 150px;
    background-color: pink;
    margin: 100px auto;
    display: flex;
  }
  p span{
     flex: 1;
  }
  p span:nth-child(2){
    flex: 2;
    background-color: lightskyblue;
  }
```

![image-20210914185954911](D:/typora笔记/工作遇到的问题/img/image-20210914185954911.png)

##### b.align-self

控制某一个子盒子自己在侧轴的排列方式

```html
  section {
    width: 60%;
    height: 400px;
    background-color: pink;
    margin: 0 auto;
    display: flex;
  }
  section div{
    width: 100px;
    height: 100px;
    background-color: rgb(144, 225, 240);
    margin-right: 10px;
  }
  section div:nth-child(1){
  align-self: center;
  }
    <section>
    <div>1</div>
    <div>2</div>
    <div>3</div>
  </section>
```

<img src="D:/typora笔记/工作遇到的问题/img/image-20210914193211771.png" alt="image-20210914193211771" style="zoom:67%;" />

##### c.order

order属性定义子项的排列顺序（前后顺序）

数值越小，排列越靠前，默认为0

```
  section {
    width: 40%;
    height: 300px;
    background-color: pink;
    margin: 0 auto;
    display: flex;
  }
  section div{
    width: 100px;
    height: 100px;
    background-color: rgb(144, 225, 240);
    margin-right: 10px;
  }
  section div:nth-child(3){
  order: -1;
  }
```

![image-20210914193450010](D:/typora笔记/工作遇到的问题/img/image-20210914193450010.png)