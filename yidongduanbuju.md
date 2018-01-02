移动端布局
==
1. 像素：计算机屏幕能显示一种特定颜色的最小区域
   * 设备像素---》实际像素
   * 逻辑像素---》页面中显示的像素
2. 视口
   * 布局视口（一般980px）(没有响应式，为了方便观看)
   * 视觉视口（css像素的数量会随着用户缩放而改变）
   * 理想视口 （meta标签来定义理想视口，）meta name="viewport" content="width=device-width"
   * 缩放 meta name="viewport" 。。。
       1. initial-scale 设置页面的初始缩放程度和布局视口的宽度 1
       2. minimum-scale 最小缩放程度
       3. maximun-scale 最大缩放程度
       4. user-scalable 是否允许用户缩放 no
       5. width         设置布局视口的宽度为特定的值 device-width
   *  <meta name="viewport" content="width=device-width,initial-scale=1,user-scalable=no" />
3. 测试网页
    * 浏览器的自带工具
    * 电脑上的模拟器
    * 在手机上进行测试
4. 移动端兼容
    * css -webkit- -moz-
    * js  webkit moz 前缀
5. 移动端布局   (移动端常见分辨率320 375 360 414)
    * 固定宽度320px简单和pc端布局方式一致 显示太大 视觉效果不好
    * 百分比布局 自动适应设备的宽度 高度(padding-top)和 边距(margin-top)等都通过百分比来计算，只能用于一些简单页面的布局
    * 响应式布局 针对不同尺寸可以进行适应 使用与pc端和手机端使用同一套代码的时候
    * rem布局（简单高效）rem(css3新增单位)
    * flex布局（css3新属性 兼容性问题多 ）http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html?utm_source=tuicool（详细说明）
        * 容器的属性
            * display：flex / inline-flex;
            * flex-direction:row|row-revese|column|column-revese 主轴的方向
            * flex-wrap:wrap 换行
            * flex-flow:row wrap ;以上两个属性的简写
            * justify-content:flex-end|flex-start|center|space-around(空隙)|space-between （包括两边）项目在主轴上的对齐方式
            * align-content:flex-start|flex-end|center|space-between | space-around | stretch(多行项目在交叉轴的对齐方式)
            * align-items：flex-start | flex-end | center | baseline | stretch;（是定义单行在交叉轴的对齐方式）
        * 项目的属性
            * order 排序
            * flex-grow 放大
            * flex-shrink 缩小
            * flex-basis  在分配多余空间之前，项目占据的主轴空间（main size）
            * flex:0 1 auto;是flex-grow flex-shrink flex-basis的简写
            * align-self:auto | flex-start | flex-end | center | baseline | stretch;
                         }允许单个项目有与其他项目不一样的对齐方式
6. 移动端事件
    * touchstart（触摸开始）
    * touchmove（触摸移动）
    * touchend（触摸结束）
    * touchcancel(不常用)
    * onorientationchange(屏幕旋转事件)
    * click
7. zepto.js  简化本的jquery；适合在移动端使用  封装了一部分移动端事件
8. touch.js  移动端的函数库 包含很多事件
9. swiper jquery插件 用于制作移动端的各种轮播 图效果