1. 安装phpcms步骤
	1. 解压
	2. 将install_package中的文件全部剪切到项目文件夹下面 project
	3. 打开浏览器 输入localhost/project/install
	4. 默认安装
		1. 数据库账号root
		2. 数据库超级管理员账号密码自己去设置
	5. 安装完成之后做个验证
		1. localhost/project
		2. localhost/project/admin.php 
2.  css js  img文件的引入   
	1.  后台模板的默认路径在project/statics/css||js||image
	2.  css     {CSS_PATH}
	3.  js      {JS_PATH}
	4.  img     {IMG_PATH}
3.  头尾分离(\wamp\www\project\phpcms\templates\default\content)
	1. header.html---->备份
	2. index.html----》备份
	3. footer.html---》备份 