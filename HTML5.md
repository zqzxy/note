H5
==
1. SGML 通用标记语言
2. html5中为何不用进行文档说明
    * html5不是基于SGML,因此不需要进行文档声明
3. 标签
    * section 区域的章节表示
    * hgroup  对标题进行组合
    * header
    * footer
    * nav
    * article 文章的主体内容
4. 块级型标签
    * aside    用于表示注记 摘要 文章资料等
    * figure   放置一些audio  video标签等流内容
    * figcaption  流内容的标题
    * code     放置代码
5. 行内标签
    * meter     表示特定范围内的数值 max min value(进度条的效果)
    * time      表示时间 属性datetime用来强调时间
        1. datetime="2017-11-11"
        2. time标签不会在任何浏览器中呈现任何特殊效果。
    * progress  表示进度  （进度的效果）
        * value(当前完成多少)
        * max="" 表示最大是多少
    * canvas
    * video,audio
        * video标签身上的属性
            1. autoplay="autoplay" 自动播放
            2. controls="controls" 播放器控件
            3. height="100px"      播放器高度
            4. width="100px"       播放器宽度
            5. src=""              播放器视频连接
            6. loop="loop"         循环播放
6. 属性
    * contenteditable
        *   表示内容是可编辑的，除了本身内容就可编辑的标签之外，其他标签均可以使用
        *   值： true||false
    * draggable 可以拖放
    * hidden    元素直接隐藏
7. 表单控件
    * 可以不用放在form中了，可以放在页面的任意位置 给form一个id,其他控件使用form属性指向form标签
        1. <form id="aa"></from>  <input type="text" form="aa">
    * email  设置完成一定要加上name属性 电子邮件地址
    * url
    * 表示时间的(火狐不支持)
        1. date  日期
        2. time  时间
        3. month 月份
        4. week
        5. datetime 火狐和谷歌不支持  datetime-local 完整时间
        6. number 数值类型 max min  number step(每次跳的时间的个数)
        7. range  也是用来表示数值的max min number step
        8. search 搜索
        9. tel   表示电话
        10.color 颜色
8. html5 新属性
    * placeholder 默认的提示文字 点击不会消失
    * required  请填写此字段
        1. required|required=required
    * pattern   进行正则验证
    * autofocus 自动聚焦
    * autoconplete 自动完成或是自动补全 on|off
    * novalidate  是否需要验证的
    * multiple   多选
    * submit当中 重写表单的属性 formaction formmethod formnovalidate formenctype
    * file accept 上传需要什么格式
	*	<datalist><option>数据</option></datalist>
拖放
==
1. draggable="true|false" 表示一个元素是否能被拖拽\
2. 对于被拖拽的元素来说 ondragstart ondrag  ondragend
3. 对于投放区域 ondragenter ondragover ondragleave ondrop 是针对鼠标的位置来触发的
4. dataTransfer   通过setData和getData可以传递信息
5. 案例：简单的一个拖放

文件
==
1. file API文件获取
2. fileReader对象： 文件读取      var fr=new FileReader()
3. ev.dataTransfer.files[0]，得到文件信息   通常要加一个下标
4. fr.readAsDataURL()将fileReader对象身上的readAsDataURL()方法编码成对应的url
5. fr.onload=function(){}输出结果
3. 补充：post比get多一次请求
4. input type="file" name="file" accept=""(可以限制上传的格式)
5. var formdata=new FormData 用来保存表单提交的数据
本地存储
==
* 必须是同域的  在同一个域名下 ajax 默认不能跨域的（有办法可以使其跨域）
   * 端口号不一致 不属于同域
   * 协议不一致 不属于同域
   * 一级域名和二级域名也不属于同域
   * 文件夹不同属于同域
1.localStorage
   * 和cookie对比  存储的数据量很大 5-10MB
   * 存储的数据永远不会自动消失 除非主动删除
   * 操作简单
   * 只能存储字符串 会把不是字符串格式的数据直接转换
   * 例如：localStorage.aa="bb";
        * localStorage["bb"]=2;
        * alert(typeof (localStorage.bb));
        * localStorage.setItem("cc","3");
        * alert(localStorage.aa);
        * alert(localStorage["aa"]);
        * alert(localStorage.getItem("cc"));
        * localStorage.clear();//一次性的清空掉全部数据
        * alert(localStorage.key(0))名字
   * JSON.parse()  将字符串解析成对象 
   * JSON.stingify() 将对象解析成字符串
2. sessionStorage(一个会话)
    * 只能存储一个会话阶段的数据
    * 和localStorage 拥有完全相同的api
    * 使用方式和localStorage一样
画布(canvas)  canvas这是一个标签  行内块标签
==
1. canvas标签的宽高要写在标签身上 当做属性的写
##绘图环境
    * var cobj=canvas.getContext("2d") 得到一个环境对象，这个环境是二维类型的
##环境对象身上的方法
1. cobj.fillRect(50,50,100,100);//绘制一个矩形,前两个参数是位置，后两个是宽高
2. cobj.strokeRect(150,150,100,100);//绘制一个线框 
    * 参数：前两个表示位置，后两个表示大小
3. cobj.arc(x,y,r,a,b)//绘制一个圆，
    * 参数 x y  坐标   r半径  a起始角  b结束角
3. cobj.clearRect(50,50,100,100);//擦除指定区域
    * 参数：前两个表示位置，后两个表示范围
4. 路径：图形的基本元素是路径 路径是通过不同颜色 不同宽度的线段或是曲线连接成的不同形状的点的集合，每个路径都是闭合的
    * cobj.beginPath()//清空一个路径的列表，开始绘制一个新图形
    * cobj.moveTo()//把当前的笔触移动到某一个位置
    * cobj.lineTo()//从上一个坐标到当前坐标 进行路径的绘制，
    * cobj.closePath//闭合路径
    * cobj.stroke()//描边
    * cobj.fill()//填充
5. cobj.rect(x,y,width,height)//绘制矩形路径
6. cobj.fillStyle=""//red #f0f rgb() rgba()//填充的颜色
6. cobj.strokeStyle="";描边的颜色
7. cobj.quadraticCurveTo(200,150,200,100)//二次方贝塞尔曲线方法
    * 前两个是控制点的坐标，后两个是结束点的坐标
8. cobj.bezierCurveTo(130,130,160,130,200,100);//三次方贝塞尔曲线
9. cobj.globalAlpha="0.5"//调整整个的透明度
10. cobj.strokeStyle="blue";//线的颜色
11. cobj.lineWidth="10";//线的宽度  不带单位
12. cobj.lineCap="round"//线两端的样式     butt(默认)|square(方块)|round(圆角)
13. cobj.lineJoin="round"//线交点的样式    round(圆角)|bevel(磨平的效果)|meter(延伸)
14. cobj.setLineDash([4,2]);
    * 设置虚线的样式
    * 参数是数组 数组中第一个是长度，第二个是间距
15. cobj.lineDashOffset="";//设置虚线位移
16. 变形（对坐标系来变形）
    * cobj.save() 这个方法会保存当前所有的状态 包括 填充颜色 描边颜色 保存变形状态
    * cobj.restore()返回上一次的save（）
    * cobj.translate() 坐标系位移
    * cobj.rotate() 坐标系旋转
    * cobj.scale() 坐标系缩放
17. cobj.font="40px Arial";//字体设置
    cobj.textAlign="left||right||center";//水平居中
    cobj.textBaseline="middle||top||bottom";//文字基线的位置
    cobj.fillText(i,0,0);//设置字体的位置
18. 线性渐变
    * var lin=obj.createLinearGradient(0,0,200,200);//设置渐变的方向
    * lin.addColorStop(0,"#fff")//第一个参数是位置，第二个是颜色
19. 径向渐变
    * `var rad=obj.createRadialGradient(x,y,r,x0,y0,r0);
        * 参数 x y 开始圆的坐标   r开始圆的半径   x0 y0 r0 结束圆的坐标和半径
    * `lin.addColorStop(0,"#fff")//第一个参数是位置，第二个是颜色
20. 图片加载
    * //浏览器还没有加载这些图片  图片的预加载
    * //1.把所有需要加载的图片都获取到
    * //2.遍历所有的图片 为每一个图片创建一个img对象
    * //3.给每一个img对应的src属性
    * //4. 给每一个image 对象注册onload事件
    * //5. 所有的图片都加载完成之后 进行页面的跳转
21. 嵌套
    * `obj.fill("evenodd");//按奇偶数的方法填充`
    *  obj.shadowOffsetX=5;
         obj.shWdowOffsetY=5;
          obj.shadowBlur=5;
          obj.shadowColor="red";
22. 绘制图片
    * drawImage//obj.drawImage(img,250,250,100,100);//2 3 位置  4 5 插入图片的宽高（伸展或是缩小）
    * drawImage(img,x,y,width,height,x0,yo,width0,height0);//截取图片
        * img 就是获得的dom元素
        * x,y,width,height 截取的图片的坐标和大小
        * x0,y0,width0,height0;画布中图片的坐标和大小
23. 像素操作
    * getImageData 为画布上指定的矩形复制像素数据
    * putImageData 放回
24. 绘制正多边形（封装一个函数）





