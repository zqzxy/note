###js表单对象
1. 获取表单对象
    *  1. document.getElementsByTagName("form")[0]
    *  var msg=document.getElementsByTagName("form")[0];
    *  2. document.getElementsByClassName("")
    *  3. document.getElementById()
    *  4. document.getElementByName()
    *  name和class的区别 
	    *  name平时都是在表单标签中使用的，class哪里都可以用
    *  var form=document.getElementsByName("msg")[0];
    *  5. document.name(只适用于表单)
2. 获取表单元素
    * 表单对象.name
    * var user=msg1.user;   console.log(user)
3. 表单事件
    * 表单对象.onsubmit  提交后触发
    * 表单对象.onreset   重置后出发
    * 表单控件
        * onblur   失去焦点
        * onfocus  获取焦点
        * onchange 失去焦点并且内容改变之后触发
4. 表单属性
    * action=url    将表单提交到哪里
    * method(提交方式)
        * get（表头报文中）
        * post（协议当中）
    * name
    * elements(所有控件的集合)
    * enctype(编码的类型)
        *   默认：enctype:appciation/x-www-form-urlencoded
        *   如果提交照片、文件：enctype:multipart/form-data
5. 表单控件属性
    * disabled=true|false  设置表单是否被禁用
    * readyOnly="readyOnly" 设置表单是否是只读
6. select的值
    * options 所有选项集合
    * size    显示个数
    * multiple 是否多选
    * selectedIndex 当前被选中项的索引值
7. option的值
    * index 当前选项索引值
    * value  值
    * text   文本内容
    * selected   是否被选中状态
8. 选择控件（单选框 复选框（多选））
    *   checked 获取或是设置某一选项是否被选中  true选中   false 未选中
    *   checked=true||false
9. 全选反选    城市三级联动   背景切换