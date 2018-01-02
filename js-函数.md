##js_函数
	定义：就是将具有特定功能的代码块集合起来，随处使用，
###如何去创建一个函数？
	1.	function 函数名(){}    {}---------》函数体
	2.	以字面量的形式创建
		就是将一个函数给了一个变量
		var aa=function(){}
	3.	以对象的形式来创建
		var b=new Function();
		new(实例化)     Function()-------->构造函数
###如何去调用一个函数
	1.	函数名（）
	2.	字面量名（）
	3.	事件触发
		onclick（点击） onmousemove（鼠标经过时）  onmouseup（鼠标抬起时）   onmousedown（鼠标按下时） onmouseover（鼠标在它上方时） onchange(鼠标获得焦点并内容改变时触发) onmouseout(鼠标离开的时候)
		案列：
			div.onclick=function(){}
		扩展：
			1.	通过标签名去获取这个DOM对象（标签，盒子）
				document.getElementsByTagName("标签名")；  []
			2.	如何去改变标签里面的内容
				innerHTML="";(一定是一个字符串)
				DOM对象.innerHTML=""
			3.	如何去改变一个DOM对象的样式
				举例：  div.style.width="200px"  
	4.	函数自调用
		function a(n){}(1);
###形式参数和实际参数（形参 实参）
	function move(a,b){
 		var max;
		if(a>b){
			max=a;
			console.log(max)
		}else{
			max=b;
			console.log(max)
		}	
	}
	move(2,3)
	形参： a  b
	实参： 2  3
###arguments
	arguments是当我们在创建函数的时候，就会自动创建一个arguments对象
	功能：
		1.	可以输出整个函数    arguments.callee
		2.	可以得知参数的个数  arguments.length
		3.	可以得知每个参数的值  arguments[]
###任务
	1.	整理好笔记
	2.	每一个知识点写一个小例子
	3.	函数调用里面事件触发的写一个有意思的练习




	
