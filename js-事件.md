##事件（动的||操作）
###定义：
	浏览器检测的用户的一些操作或者页面的一些行为
	onclick onmousemove onmouseover onmousedown onmouseout onblur  onfoucs onchange
###事件的组成
	div.onclick=function(){
		alert(1)
	} 
	div------------>事件源
	onclick-------->事件
	function(){}--->事件处理程序
###添加事件监听
 	实质：就是给元素添加事件，但是可以给一个元素同一个事件添加多个事件处理程序
 	addEventListener(a,b,false)
	 	a--->事件(没有on)
	 	b--->事件处理程序(放在外面来写)
	 	false->程序由里向外执行
	 	true-->程序由外向里执行
 	存在兼容性（ie6-8中）
 	attachEvent(a,b)
 		a----->事件（onclick）
 		b----->事件处理程序
		obj.attachEvent("onclick",function(){})
###消除事件 注销事件
	obj.onclick=function(){}----->div.onclick=null
	obj.removeEventListener(a,b,false)
		a----------->事件
		b----------->事件处理程序
	存在兼容性（ie6-8中）
		obj.detachEvent("onclick",function(){})
###兼容性函数addEvent()  removeEvent()
	//参数一 表示事件源
	//参数二 事件名称
	//参数三 事件处理程序
	function addEvent(obj,event,handler){
		if(obj.addEventListener){
			obj.addEventListener(event,handler,false);
		}else{
			obj.attachEvent("on"+event,handler)
		}
	}
	function removeEvent(obj,event,handler){
		if(obj.removeEventListener){
			obj.removeEventListener(event,handler,false);
		}else{
			obj.detachEvent("on"+event,handler)
		}
	}
##事件对象
1. 定义：用来记录事件触发的时候的一些细节的对象，在事件处理程序中设置形式参数e，这个参数可以作为事件对象
	*	e.offsetX  e.offsetY  距离事件源的坐标
	*	e.clientX  e.clicntY  距离可视窗口的坐标
	*	e.screenX  e.screenY  距离屏幕的坐标
2. 存在兼容性（浏览器的兼容）
	* ie6-8识别  window.event
	* 火狐识别   e
	* 谷歌都识别
	*	兼容性的获取事件对象  var ev=e||window.event
##任务
	1. 点击换色
	2. 拖拽






