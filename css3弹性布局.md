#css3 Flex弹性布局
*** 

> display:flex 多栏多列布局 css3提供的新属性 方便手机端进行布局，浏览器支持情况较差 用来为盒装模型提供最大的灵活性

* display:flex / display:inline-flex

特性
--
* 任何一个容器都可以使用弹性布局 (所有标签都可以用)块元素使用display:flex;行内元素使用display:inline-flex;

* 对于webkit内核浏览器 前缀的添加方式 display:-webkit-flex;

* 设置flex之后，子元素的float、clear、和vertical-align属性将失效

* 采用flex布局的元素被称为flex container 简称容器，子元素会自动转化为容器成员，成为flex item 简称项目； 

![图片1](demos/flex/1.png)
##flex容器的基本结构
* 容器默认存在两根轴，水平的主轴 main axis 和垂直的交叉轴 cross axis 主轴的起始位置叫做main start 结束位置叫做 main end 交叉轴的起始位置叫做 cross start结束位置叫做 cross end
* 项目默认沿主轴排列，占据主轴的空间叫做main size 占据交叉轴的空间叫做cross size；

属性（全部给父级（容器加）加）
--
* 容器的属性
  1. flex-direction 
  2. flex-wrap
  3. flex-flow
  4. justify-content
  5. align-items
  6. align-content
### flex-direction 方向
      .box{
         display:flex;
         flex-direction:row|row-reverse|column|column-reverse;
       }
 > * row 默认值 主轴为水平方向，起点在左端 
 > * row-reverse 主轴为水平方向，起点在右端 
 > * colunm 主轴为垂直方向，起点在上沿
 > * column-reverse 主轴为垂直方向，起点在下沿
 
### flex-wrap 换行
      .box{
      display:flex;
      flex-wrap:wrap|nowrap|wrap-reverse;
      } 
 > * 默认情况下 项目都排到一条轴线上，当轴线上放不下的时候，
 > * flex-wrap定义如和换行 
 > * no-wrap不换行 
 > * wrap换行 第一行在上方 
 > * wrap-reverse 换行 第一行在下方

### flex-flow
      .box{
       display:flex;
       flex-flow:row nowrap;
       }
> flex-flow是flex-direction和flex-wrap的简写形式

###justify-content
       .box{
       display:flex;
       justify-content:flex-start|flex-end|center|space-between|space-around;
      }
> * 定义项目在主轴上的对齐方式
> * flex-start（默认值）：左对齐 
> * flex-end：右对齐 
> * center： 居中
> * space-between：两端对齐，项目之间的间隔都相等。
> * space-around：每个项目两侧的间隔相等。所以，项目之间的间隔比项目与边框的间隔大一倍。

![图片2](demos/flex/2.png)
### algin-items 
      .box{
       display:flex;
       align-items:flsx-start|flex-end|center|baseline|stretch
      } 
> * align-items属性定义项目在交叉轴上如何显示，一行的使用（交叉轴方向）
> * flex-start：与交叉轴的起点对齐。
> * flex-end：与交叉轴的终点对齐。
> * center：与交叉轴的中点对齐。
> * baseline:与文字基线对齐
> * stretch：项目占满整个交叉轴。

![图片3](demos/flex/3.png)
### align-content
     .box {
      display:flex;
      align-content:flex-start|flex-end|center|space-between | space-around | stretch;
      }
> * align-content属性定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。
> * flex-start：与交叉轴的起点对齐。
> * flex-end：与交叉轴的终点对齐。
> * center：与交叉轴的中点对齐。
> * space-between：与交叉轴两端对齐，轴线之间的间隔平均分布。
> * space-around：每根轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间隔大一倍。
> * stretch（默认值）：轴线占满整个交叉轴。

![图片3](demos/flex/4.png)

 

* 项目的属性
  1. order
  2. flex-grow
  3. flex-shrink
  4. flex-basis
  5. flex
  6. align-self
### order
     .item {
      order: <integer>;
      }
> order属性定义项目的排列顺序。数值越小，排列越靠前，默认为0。

###flex-grow
     .item {
      flex-grow: <number>; /* default 0 */
     }   
>flex-grow属性定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大。如果所有项目的flex-grow属性都为1，则它们将等分剩余空间（如果有的话）。如果一个项目的flex-grow属性为2，其他项目都为1，则前者占据的剩余空间将比其他项多一倍。
### flex-shrink
     .item {
     flex-shrink: <number>; /* default 1 */
    }
>flex-shrink属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。如果所有项目的flex-shrink属性都为1，当空间不足时，都将等比例缩小。如果一个项目的flex-shrink属性为0，其他项目都为1，则空间不足时，前者不缩小。负值对该属性无效。
### flex-basis
        item {
       flex-basis: <length> | auto; /* default auto */
       }
>flex-basis属性定义了在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小 它可以设为跟width或height属性一样的值（比如350px），则项目将占据固定空间。
### flex
>flex属性是flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1 auto。后两个属性可选。该属性有两个快捷值：auto (1 1 auto) 和 none (0 0 auto)。建议优先使用这个属性，而不是单独写三个分离的属性，因为浏览器会推算相关值。
### align-self
    .item {
      align-self: auto | flex-start | flex-end | center | baseline | stretch;
    }
>align-self属性允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。默认值为auto，表示继承父元素的align-items属性，如果没有父元素，则等同于stretch。该属性可能取6个值，除了auto，其他都与align-items属性完全一致。