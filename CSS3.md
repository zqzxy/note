****css3---http://nate-river.github.io/css3/
==
  1. 背景边框的样式  过渡效果  2d、3d转换效果  文字的属性  选择器  布局 帧动画 响应式布局（重点） less（sass）  bootstrage  移动端布局和移动端事件
  2. 选择器   
       * [attr]         属性名
       * [attr="]       属性="值"
       * [attr^=""]     选中开始的位置是指定值的
       * [attr$=""]     选中结束的位置是指定值的
       * [attr*=""]     选中当中包含指定值的
       * [attr|=""]     选中开始位置是指定单词
       * [attr~=""]     选中当中包含指定单词
       * ：root         选中文档的根元素
       * 重点
	       * ：nth-child(n) num|even(偶数)|odd（奇数）|2n|2n-1|3n 计数是从1开始的 nth-of-type 同类标签中的第N个
	       * ：first-child  第一个子元素   first-of-type  同类标签中的第一个
	       * ：last-child   最后一个子元素 last-of-type   同类标签中的最后一个
		       * child 只考虑在所有子元素当中的位置，type值考虑在同类标签中的位置
       * ：only-child   只有一个子元素的
       * ：nth-last-child()  从最后开始计数
       * ：empty        选择内容为空的元素
       * ：focus           获得焦点的时候
       * 重点
       	   * ：before  元素的内容之前插入（插入的是行标签）
       	   * ：after   元素的内容之后插入 （插入的是行标签）
       	   	   * ：after{content:" ";display:block;clear:both;}
       * http://a.singlediv.com(用div制作的图标)
       * div+p          紧跟在div后面的P标签(1)  同辈元素
       * div~p          在div后面的P标签(全部)     同辈元素
       * div>p          子选择器
       * 补充：
           * document.querySelector()选择某个元素， 参数就是css选择器
           * document.querySelectorAll()选择某个集合  参数就是css选择器 
  3. 颜色 边框  
	  * #fff red  rgb(255,255,255) rgba(255,255,0,0.8)其中的a代表透明度
	  * outline：宽度  样式  颜色；表示描边 （不参数位置的计算只是一个效果）
        *  描边不会随着圆角改变
        *  描边只是效果 不占位置   
        *  没有单一的方向 只能同时设置四个方向
 	    *  outline-offset   描边的偏移  可以设置负值
 	    *  box-shadow:0 0(偏移量) 5（模糊程度）10（调整阴影的大小）red inset(内阴影)可以设置多组值 通过逗号分开  分开不占位置
           * 如果想要让阴影占位置   可以给它加外边距  
        *  box-sizing 设置或检索对象的盒模型组成模式 (可以直接在css开始设置) *{box-sizing:border-box}
           * border-box
           * content-box  
     * border-radius 可以设置多个值  四个值共有
        * border-radius:10px/20px;(可以设置两个值，椭圆的两个半径)
        * border-radius:10px 20px 10px 20px ; 
     * border-image
           * border-image-source ：url()图片的路径
           * border-image-slice:33      截取的偏移量
           * border-image-width:33px;   边框的宽度
           * border-image-repeat:round（完整的去重复）/repeat 边框重复方式
           * border-image-outset:16px;  超出容器的偏移量 只是效果 不会影响布局   
     * css3  linear-gradient()   radial-gradient()
           * 是用来生成渐变图案的  类似于图片 但是没有尺寸 没有大小限制  
           * background-image:line...    border-image
           * 线性渐变 (linear-gradient())
           	 * deg
             * to left|top|bottom|right|
             * to top left  
             * 例子：background-image:linear-gradient(to left,white,blue,green，yellow);
             * 颜色设置：
                1. 可以设置多个颜色
                2. 每一个颜色都可以设置位置 
                  * background-image:linear-gradient(to left,white 0,blue 50%,green 50%，yellow);
                3. 位置不设置默认  平均划分
                4. 位置设为0，默认是在上一个位置继续   
                5. repeating-linear-gradient  重复的线性渐变
                6. 
           * (radial-gradient()) 
                1. 第一个可以设置形状 circle
                2. 第二个参数可以是渐变范围的大小 closest-side  farthest-side  closest-corner  farthest-corner length
                3. 第三个可以是位置 length  %  keywords  用at来连接
                4. repeating-radial-grandient() 重复的经向渐变
                5. 补充：jquery.easing.js插件（一些简单动画的插件）
 4. 背景 
     * background-clip    裁剪
        * border-box （默认）
        * padding-box
        * content-box 
     * background-origin  背景图片的定位参照
        * border-box
        * padding-box（默认）
        * content-box
     * background-size    
        * 100px 100px
        * 100px auto(等比例的放缩)
        * 50%(盒子的50%);
        * cover(优先铺满容器)等比例的放缩
        * contain(优先展示图片)  等比例的放缩
     * background  也可以设置多个值  
 5. 过渡效果   transitions(在选择器中设置)
     * transition-property  动画的属性 transition-property:width,height|all;
     * transition-duration  动画的时间 transition-duration:1.5s;
     * transition-timing-function
        * ease-in 加速 transition-timing-function：ease-in;
        * ease-out 减速
        * ease-in-out 先加速后减速
        * linear   匀速 
        * cubic-bezier(贝塞尔曲线) http://web.chacuo.net/
     *  jquery插件  jq22.com
     * transition-delay 延迟 transition-delay:1s; 
     * transform(移动端用的多)
        * transform使用时必须去和transition结合使用
            1. 父级加transition
            2. 子级加transform
        * 旋转轴是X轴 方向就是z轴方向
        * 旋转轴是y轴 方向就是x轴方向
        * 旋转轴是z轴 方向就是x轴方向(顺时针 逆时针)
        * 2d
            * translate(50px,40px) 位移     transform:translate(length[,length]?)|translateX(length)|translateY(length)|translateZ(length)
            * rotate(45deg|1rad(弧度)) 旋转 transform:rotate rotateX()|rotateY()|rotateZ()
            * scale（1.5,1.5）缩放          transform:scale(number,[number]?)|scaleX(number,[number]?)|scaleY(number,[number]?)也可以设置一个值代表横向和纵向效果一样
            * skew(45deg,45deg)斜切          transform:skew(angle [,angle]?)|skewX(angle [,angle]?)|skewY(angle [,angle]?)
            * 简单写法：transform:translate(100px,100px) rotate(45deg) skew(30deg,30deg);
        * 3d
            * translate3d(x,y,z)
        * transform-orgin(位移转换的基准点)
             * x轴和y轴的位置 length  %  left top right bottom         transform-origin:center center -800px;
        * 简单的写法：transition:width 2s ease-in 1s;
        * transform-style  用来定义子元素在一个3d场景中显示   preserve-3d
        * perspective 景深  perspective:1000px
        * perspective-origin  观察点的位置
        * backface-visibility 背面是否可见   backface-visibility:hidden/visiable
6. animation 动画效果
==
  1. @keyframes name{};定义动画
  2. animation-name   动画的名称
  3. animation-duration  动画执行一次所需的时间
  4. animation-timing-function  动画的方式
  5. animation-iteration-count  动画执行的次数 infinite(无限)
  6. animation-direction        是否反向 alternate（动画交替反向）
  7. animation-play-state       是否暂停 paused（暂停）  running
  8. animation-fill-mode   动画执行完成之后的状态 backwards(动画完成之后保持最后一帧的样式)  forwards（动画完成之后保持第一帧的样式）
  9. http://www.uedsc.com/fullpage.html
     * 自我介绍
     * 技能
     * 联系方式
     * 作品 
  10. width:100px!important;获得最高的优先级 
字体
==
1. 保持中文超出不换行的两种方式
	1. word-break:keep-all
		* normal     有连字符的地方换行
		* break-all  碰到边界就换行
		* keep-all   保持中文超出不换行  
	2. word-space:nowrap  保持中文超出不换行()
2. text-overflow:ellipsis; 
3. word-space:nowrap;text-overflow:ellipsis;overflow:hidden(文字超出部分用...代替)   
4. text-shadow：0 0 3px red;设置文字的阴影（可以设置很多个） 
字体图标的使用
==
requestAnimationFrame(fun) 帧动画
cancelAnimationFrame()停止帧动画
==

   