###DOM(文档对象模型) document object model  文档以及文档中所有的元素共同组成的模型称之为DOM   那张纸上的全部东西
1. 获取元素内容、（能不能识别html标签）
   1. 能识别html标签的
       * innerHTML()获取或是设置某一个元素的内容
   2. 不能识别html标签的
       * textContent获取或是设置某一个元素的内容   现代浏览器  obj.textContent
       * innerText(ie6-8中使用)
       * function.js     getText()
2. 设置元素的样式(属性)
	* 凡是标签内的属性，我们可以当做对象的属性来使用
    * obj.style.width="100px"; 
    * 添加类名或者id
        * 在css中写好样式，使用js添加类名就可以了、
        * obj.className+=" aa"   obj.className=obj.className+" xxx"
    * 获取所有的css样式集合
	    * window.getComputedStyle(obj,null).attr     现代浏览器
	    * obj.currentstyle(ie6-8)
	    * function.js    兼容
 	*	换色（开关） 选项卡（this.index） 
3. 节点
    * 定义：文档中每一个元素。文本。属性。都代表这一个节点，所有这些节点共同组成文档树模型（文档（这张纸上面的全部东西你都称之为一个节点））
    * 节点分类
        1. 文档节点
        2. 元素节点
        3. 文本节点
        4. 属性节点
        5. 注释节点
    * 节点的属性
        1. 关系属性
            * obj.parentNode  父节点
            * obj.childNodes   子节点
            * obj.firstChild   第一个子节点
            * obj.lastChild    最后一个子节点
            * obj.nextSibling 下一个兄弟节点
            * obj.previousSibling 上一个兄弟节点
            * 任务：那个列表来一 一来写
        2. 信息属性
            * obj.nodeType   节点的类型(number)
            * obj.nodeName   节点的名称(大写的)
            * obj.nodeValue  节点的值（1 2 3 8 9）
    * 节点的方法（重点）
        * 创建节点 document.createElement("")
            *       var one=document.createElement("元素标签名")
        * 给元素添加样式 obj.style.cssText=""
            *       one.style.cssText=""
        * 将节点插入到页面当中 父级.appendChild(子级)
            *       document.body.appendChild()
        * 删除节点
            * 父元素.removeChild(子元素)
        * 替换节点
            * 父元素.replaceChild(新节点，被替换的节点)
        * 插入节点
            * 父元素.insertBefore(a,b)表示把a插入到b前面
            * document.body.appendChild()
        * 复制节点
            * newobj=obj.cloneNode()
                1. 参数是true，则连同内容一起复制
                2. 参数是false,只复制结构和样式，不复制内容
##节点的nodeType nodeName nodeValue
	           nodeType       nodeName        nodeValue
	元素节点       1          标签名（大写）      null
    属性		   2          属性名              属性值
	文本 		   3          #text               内容
	注释		   8	 	  #content            注释文字
	文档 		   9          #document           null