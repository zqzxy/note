##js属性节点
1.	获取一个元素的属性
	*	obj.getAttribute(attrname)
2.	设置一个元素的属性
	*	obj.setAttribute(attrname,attrvalue)
3.	创建属性节点的方法
		1. var attr=document.createAttribute(attrname); 创建属性节点
	2.	attr.value=attrvalue; 添加属性值
	3.	div.setAttributeNode(attr)将属性节点添加到元素中
##获取元素的尺寸（包括内边距 边框）
1. offsetWidth 元素的宽
2. offsetHeight元素的高
##获取元素的位置
1. 不考虑定位
	* obj.offsetLeft;  元素距离文档左边的值
	* obj.offsetTop;   元素距离文档右边的值
2. 考虑定位
	* obj.offsetLeft;  元素距离父元素左边的值
	* obj.offsetTop;   元素距离子元素右边的值
##关于滚动元素位置的获取
	1. obj.scrollTop obj内部元素超出它顶部的值
	2. obj.scrollLeft obj内部元素超出它左边的值
	3. onscroll事件   滚动条事件（可视窗口）
	4. 兼容性获取可视窗口函数getWindow()  
		浏览器：谷歌使用document.body  IE火狐使用的是document.documentElement
		  扩展：怪异模式（有没有doctype）
		function getWindow(){
			document.documentElement.scrollTop=1;
			if(document.documentElement.scrollTop==1){
				return document.documentElement;
			}else{
				return document.body;
			}
		}

		html     document.documentElement
		body     document.body
	5.	通过这种方式来得知一些浏览器的内核来源
##任务
1. 页面中广告的移动
2. 兼容性函数的书写（函数库function.js）
3. 返回顶部
4. 楼层控制按钮在滚动条滚动到一定的位置时出现
5. 楼层跳转
