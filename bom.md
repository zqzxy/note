##BOM（ browser object model） 浏览器对象模型
1. bom组成部分
    *   window对象
    *   history对象
    *   location对象
    *   document对象
###window对象
1.  定义：指的就是浏览器这个整体，在js运行的语言环境中，window对象是作为全局对象（类似全局变量）来看待的
	*	js的宿主环境----》浏览器
	*	js的执行环境----》浏览器
	*	js在浏览器当中的解释执行  边解释边执行    
2.  属性
                                               
    *   关于浏览器尺寸（浏览器的可视窗口）的获取(有兼容性问题)
        1.  现代浏览器中
            *   window.innerWidth;  获取浏览器可视窗口的宽度
            *   window.innerHeight; 获取浏览器可是窗口的高度
        2.  兼容性方式
            *   document.documentElement.clientWidth;
            *   document.documentElement.clientHeight;
    *   关于时间的控制（无兼容性问题）
        1.  setInterval(function(){},time)
            *   有两个参数，分别是回调函数和时间，这个函数被调用之后，会在指定时间之后执行一次回调函数，然后每隔一段指定时间再重新调用回调函数
        2.  clearInterval()
            *   用于停止时间函数，需要接受一个参数，这个参数来自对应的setInterval的返回值（数字，从1开始）
        3.  setTimeout(function(){},1000)
        4.  clearTimeout()
        5.  setTimeout和setInterval的区别
            *   setTimeout表示在指定时间之后执行一次回调函数，但是只执行一次
            *   clearTimeout（）用于停止时间函数
        6.	任务：页面当中有三个按钮  分别是开始   暂停  继续，当我点击每一个的时候又响应的功能
	        1.	开始：div开始运动
	        2.	暂停：div运动停止
	        3.	继续：div运动继续
	        4.	进度条
    *   confirm()
        1.  用于实现确定取消的效果
    *   open() 接收三个参数
        *   第一个参数：新窗口要打开哪个网页
        *   第二个参数：新窗口名字
        *   第三个参数：新窗口的属性
    *   close()关闭直接打开的窗口  ie Chrome可以  火狐不可以（待续）
    *   获取电脑屏幕的分辨率
        1.  window.screen.width;
        2.  window.screen.height;
    *   window.onload=function(){} 触发在window身上的时间表示页面加载完成之后会触发  script标签对中window.onload只写一次
    	window.onload     $(jquery)  document.ready?(页面结构以页面内容的问题)
		他们都是实现html结构加载的同时js也加载出来
		document.ready--->html结构（图片 内容都没有出来）
    *   通过标签名来获取元素
        1.  document.getElementsByTagName()  ----》类似数组集合
    *   修改元素内容
        1.  innerHTML           div.innerHTML=""
    *   通过id名获取元素，获取的是单个元素
        1.  document.getElementById()
        2.  任务：获取一个元素的函数（放到function.js） 函数起名getEle()
###history对象(历史对象)
1.  属性
    *   history.length当前历史对象保存的历史记录信息有几条
    *   history.forward()跳转下一条历史记录
    *   history.back()跳转到上一条历史记录
    *   history.go()   参数1表示前进   0  刷新   -1 后退
###location对象  (地址（网址）对象)
    https://www.baidu.com/s?f=8&rsv_bp=1&rsv_idx=1&word=%E7%99%BE%E5%BA%A6%E7%BD%91%E7%9B%98&tn=98012088_4_dg&ch=14
    http://    https:// 协议  protocal
    www.baidu.com    //域名
    ：89               端口
    2017910/index.html    路径
    #aa   锚链接地址
    ？aa=1&bb=2&cc=3    查找字符串

    1.  URI  统一资源标识符（很久以前URI包含URL  但是现在我们把它们当做一个）
        url 统一资源定位符
    2.  属性
        location.host      访问域名
        location.protocol  访问协议
        location.href      访问完整地址 eg:location.href="www.baidu.com"
        location.hash      访问锚链接地址
        location.port     访问端口号
        location.search    访问字符串部分
        location.pathname  路径部分
        location.replace() 接受一个路径，表示页面跳转，不会留下历史记录
        location.reload() 表示刷新页面

###document对象(文档对象)
1.  属性
    *   document.body    访问body标签
    *   document.title   访问的是title的内容
    *   document.all     访问页面中全部标签
    *   document.images  访问页面全部图片的集合
    *   document.links   访问页面中所有连接（css文件）的集合
2.  方法
    *   document.getElementsByTagName("")//通过标签名获取元素
    *   document.getElementById()//通过id名来获取元素
    *   document.getElementsByClassName() 通过类名获取元素  存在兼容性问题（document.getElementsByClassName() ie8以下没有这个方法）
    *   关于获取元素的一个函数（getEle）；
