AngularJS ( 谷歌开发的前端开发js框架 )
==
* https://code.angularjs.org
* https://github.com/angular/angular.js
* 官方网址：https://angular.org
* 手册https:https://docs.angularjs.org
* 中文手册api:http://www.angularjs.net.cn/api/
* https://github.com/angular/angular.js.git
简单认识
==
1. 概念关键词：数据绑定、DOM操作、MVC设计模式、模块化加载
    1. 数据
        * 前端页面 展示数据
        * 数据存储在服务器的数据库中
    2. 前端要做的工作
        * 页面常见的交互效果 js css3
        * 对于后台返回的数据的处理
        * 如何把数据更好的展示在界面上
        * ajax 操作数据 发送 获取
          - 1. 创建一个ajax对象   xhr
          - 2. 书写请求xhr.open("get||post",url)   发送请求xhr.send(data)
          - 3. 服务器回应
                xhr.onreadystatechange=function(){
                  if(xhr.readyState==4){
                    if(xhr.status==200){
                      text  responseText;
                      xml   responseXML;
                      json  JSON.parse("str")   JSON.stringify()
                    }
                  }
                }
        * 去处理后台的一些数据
2. 核心：AngularJS通过指令扩展了html（基于html）
3. AngularJS主要适用于
    * 单页面Web应用
    * （大量的数据操作） CRUD的（增 删 改 查）管理系统开发
    * 开发前后端分离式的应用
    * 前后端交互频繁、大量的AJAX操作
4. AngularJS不适合类型开发
    * 内容网站，需要SEO(搜索引擎优化)的
        * SEO是指通过站内优化使网站满足搜索引擎收录排名需求，在搜索引擎中提高关键词排名，从而吸引精准用户进入网站，获得免费流量，产生直接销售或品牌推广(百度)
    * 交互频繁的，如游戏之类的交互体验网站
    * 太过于简单的页面
5. AngularJS历史：2012年发布（详细的历史，了解性的东西去了解）
6. AngularJS核心思想
    * 依赖注入
    * 模块化
    * 双向数据绑定（MVVM）
      - <input type="text" ng-model="name"/>
      - <p>{{name}}</p>
    * MVC
    * 指令
7. 为何使用AngularJS?(好处)
    * 减轻服务器压力
    * 减少DOM操作
    * 加快了开发速度
    * 体会最深的是Angular能够将关注点分离的非常彻底（视图分离）；服务层（AJAX请求）-业务层（Controller）-展现层（html模板）-交互层（animation）

    * html当中的一个知识补充：分层
        1. 文档层  第0层
        2. 漂浮层  第0.5层
        3. 定位层  第1层
8. 库VS框架
    * jquery是一个库，库总是被动的，就像工具，应用的逻辑是你的，在某一点上需要用一下工具就好了，
    * 框架：AngularJS为应用已经搭起了一个架子，约定了一些组成部分，并且实现了这些部分的拼装运行
9. angularjs是一个MVC模式的前端开发框架
10. MVC
    * M model 数据模型
    * V view  视图（html）
    * C controller 控制器
    * 举例来解释
        1. M 数据     仓库
        2. C 控制器   厨师
        3. V 视图     餐桌
    * 优点：使开发时间得到相当大的缩减，它使程序员集中精力在业务逻辑
11. AngularJS应用组成（三大组成部分）
    * 模型
    * 视图　ｖｉｅｗ
    * 控制器 管理页面的逻辑代码
12. 数据模型
13. Angularjs开发优势
    * 分离前后端关注点,前端负责界面显示，后端负责数据存储和计算，各司其职，不会把前后端的逻辑混杂在一起
    * 减轻服务器压力，服务器只用出数据就可以，不用管展示逻辑和页面合成，吞吐能力会提高几倍
    * 同一套后端程序代码，不用修改就可以用于Web界面，手机，平板等多种客户端
14. 业务逻辑---》封装好的函数一样
    * 不同的项目有不同的功能，不同的功能需要不同的实现，实现这些核心功能的代码就叫业务逻辑
15. 常用指令
    * 指令：指令是我们用来扩展浏览器能力的技术之一，在dom编译期间，和html元素关联着的指令会被检测到，并且被执行，这使得指令可以被dom使用
    * ng-app 这一个指令的功能是告诉引入的angularjs页面中的那一部分开始接收它的管理（启动Angularjs）
        1. 当前页面唯一
        2. 也可以添加到某个标签上，表明在这个<div>范围内被angular管理
        3. 一般绑定在html标签上
    * ng-model 用来进行双向数据绑定 mvvm  用于表单
        1. 为应用数据提供类型验证
        2. 为应用程序数据提供状态
        3. 为HTML元素提供CSS类
        4. 绑定html元素到html表单
    * ng-init 初始化应用程序数据
        * `<p ng-init="name='lisi'；age='19'"></p>`
    * ng-bind 把应用程序的数据绑定到视图(单向的数据绑定)
        * `<p ng-bind="name"></p><span ng-bind="name"></span>>`----依赖于标签
    * ng-controller 把控制器和视图进行绑定
    * ng-repeat 遍历输出数据(复制)
        * $index $first $last $middle $even $odd;
            1. $index 当前索引。
            2. $first 当循环的对象存在第一项时为true。
            3. $middle  当循环的对象存在中间项时为true。
            4. $last 当循环对象存在最后一项时为true。
            5. $even 循环的对象在当前位置的"$index"(索引)是偶数则为true，否则为false。
            6. $odd 循环的对象在当前位置的"$index"(索引)是奇数则为true，否则为false。
        * track by $index;
    * ng-show
    * ng-hide
    * ng-if 对DOM节点添加、删除操作
        1. 接收bool值
        2. 在ng-repeat的时候，每条数据由包含了辅助的数据结构的时候效果特别明显。当它的值为true时，
    * ng-switch 指令根据表达式(或是当前值)显示或隐藏对应的部分
        1. 对应的子元素使用ng-switch-when指令，如果匹配选中选择显示，其他为匹配的移除
        2. 可以通过使用ng-switch-default 指令设置默认选项，
    * ng-class ng-class="{'class1':true,'class':false}"
        1. 字符串数组形式
            * <div ng-class="{true:'big',false:'small'}[false]"></div>
        2. 对象key/value处理
            * <div ng-class='{'big':true,'small':false}'></div>
        3. 动态绑定class
            * <div ng-controller='ClassCtrl'ng-class='dynamicClass'></div>
    * ng-class-even 类似ng-class 但只是在偶数行起作用
    * ng-class-odd 类似ng-class 但只是在奇数行起作用
    * ng-style 表达式返回由CSS属性和值组成的对象(用于添加样式)
        1. ng-style='{}' ng-style='css'
        2. 添加形式是一个对象
          1. {width:"200px",height:"200px",background:"red"}
    * ng-href 添加链接（支持表达式）
    * ng-src 添加链接(支持表达式)
    * ng-include用于包含指定的外部的HTML文件
        1. ng-include='tpls/'list.html''
#创建一个模块
1. angular.module('模块名'，[])
    * 第一个参数 自定义模块
    * 第二个参数　模块名称（Ａｒｒａｙ）
#自定义控制器
* 控制器是用来管理视图的
* $scope(它是一个对象)作用域-控制器层和视图层的桥梁
* $rootScope 全局的一个作用范围
* `<div ng-controller="控制器名称"></div>`
1. app.controller('控制器名'，function($scope){

    })

#angular表达式
##angularjs  {{可以使用运算符}}
1. nodejs npm 包管理工具
     * 安装包
     * npm install 包名
     * npm install 包名@0.x.x
     *
2. AngularJS表达式
    1. 表达式是运用在视图中的一个代码片段
    2. 写在双大括号中{{表达式}}
    3. 在表达式写的位置输出数据
    4. 可以包含文本、运算符、变量
    5. 把数据绑定到html
    6. 自加，自减不可以
    7. 字符串用+链接
    8. 对象的访问
        * {{obj.name}}
        * {{obj.say()}}
    9. 数组的访问
        * {{arr[1]}}
    10. 也支持逻辑表达式
        * {{10&&arr[1]}}
3. AngularJS控制器
    * 控制器生存周期：只要页面重新加载或是视图切换，数据就会清空
    * 控制器作用
        1. 操作$scope对象
            * 对$scope添加属性
            * 对$scope添加方法 实现业务逻辑
            * $scope方法 作为事件处理程序
            * `<div ng-click="aa()"></div>`
        2. 处理页面逻辑(事件)
4. 自定义控制器(两种写法)的步骤
    1. ng-app=“app” 模块名
    2. js中 创建模
     第一种方法：
      ` var app=angular.module('app',[]);`
        `app.controller(ctrlname,function($scope){`
            `$scope//是一个普通对象，用来实现模型、视图、控制器三者之间的联系`
        `)`
    第二种方法：
      ` var app=angular.module('app',[]);`
    `app.controller(ctrlname,["$scope","$window",function(aa,$w){`
       ` aa.a=100;`
    `])`
5. AngularJS中事件(和js的基本一致)
    * ng-click
    * ng-mouseup
    * ng-mousemove
    * ng-mousedown
    * ng-mouseover
    * ng-mouseout
    * ng-keydown
    * ng-keyup
    * ng-press
    * ng-submit
    * ng-focus/blur
    * ng-cloak 防止angularjs代码未加载完而出现的问题
    * ng-copy 拷贝事件的行为
    * ng-cut 剪切事件的行为
    * ng-paste 粘贴事件的行为
    * 表单指令
        1. ng-value
        2. ng-checked
        3. ng-selected
6. $scope
    * 是用来定义应用业务逻辑、控制器方法和视图的地方
    * 作用域是应用状态
    * 可以任意添加属性和方法
    * 调用$scope身上的方法
        1. 表达式调用$scope对象的方法
        2. 事件调用$scope对象的方法
    * $window-->可视窗口   window对象
7. $rootScope（根作用域）
    * 可以认为是全局变量
    * app.run(function($rootScope){$rootScope.aa=111;})
8. $scope对象的生命周期
    1. 创建：在创建控制器的时候 angularjs会创建一个新的作用域，并传递到控制器中
    2. 链接：angular开始运行时，所有的$scope对象都会附加链接到视图中
    3. 更新：当事件循环运行时，它通常执行在顶层$scope对象上（$rootscope）每一个子作用域都执行自己的脏值检测，每个监控函数都会检查变化。如果检测到任何变化，$scope对象就会触发指定的回调函数；
    4. 销毁：当一个$scope在视图中不在需要时，这个作用域将会清理和销毁自己
# 常用的过滤器
1. currency 格式化数字为货币格式
  * {{car|currency:'￥':1}} (可以指定保留小数位数)
2. filter 从数组项中选择一个子集，并将其生成一个新数组返回。 数字、字符串都可以过滤
  * 过滤对象 ng-repeat="v in user|filter:{'$':search}" 过滤全部用$ 单独就写对应属性
  * js中使用过滤器
    * $filter 注入控制器中
    * $filter('过滤器名称')('数据',参数1,参数2,...)  
      * app.controller('c',function($scope,$filter){$scope.name=$filter('uppercase')($scope.name)});
3. lowercase 格式化字符串为小写
4. uppercase 格式化字符串为大写 {{name|uppercase|lowercase}}
5. number 表示保留小数位数
6. date 格式化日期的格式
  * {{time|date:'medium}}
  * {{time|date:'yyyy-MM-dd hh:mm:ss'}}
  * {{time|date:'HH:mm:ss EEE a'}} HH表示24小时制 EEE星期(Fri) EEEE(Friday) a上午/下午
7. orderBy 根据某个表达式排列数组 第一个参数必须写，第二个参数可选 '+字段名' '-'
8. limitTo 获取指定长度数组或字符串 通过传入参数的正负来判读从前面还是从后面截取
#自定义过滤器
1. app.filter('过滤器名',function(){return function(str,val1,val2,val3...)}) str要过滤的字符 val1,val2,val3...0
#补充
1. {{}} 变量 运算符 函数调用
2. ng-class="'box'" 类名
3. ng-class="box" 变量
4. angular.foreach();
5. module.run(function($rootScope){$rootScope})
6. module.controller('控制器名'，['$scope',function(){}])
7. module.filter('过滤器名'，function($filter,$window,$timeout){return function(str,v1,v2,...){})
#过滤器（一共有八个）
8. currency 格式化货币{{1000|currency：'￥'：1}}
9. lowercase大小写转换
10. uppercase大小写转换
11. number 小数位数
12. date 格式化日期
13. {{time|date:'yyyy-mm-dd hh-mm-ss EEEE a'}}
14. {{time|date:'yy年mm月dd日 HH-mm-ss EEEE a'}}
15. filter 过滤
    * {{filter：'10'}}返回过滤后的数据
    * {{filter：{'$':'zhangsan'}}}
16. orderBy 排序
    * + -
    * {{arr|orderBy:'-'}}
    * 如果是一个json数据  {{arr|orderBy:'+age'}}
    * 特殊排序（函数）{{arr|orderBy:ord}}
        * function ord(arr){arr.length=2;return arr;}返回过滤完成之后的结果
        * function ord(arr){var newarr=arr.sort(function(a,b){return a.name.localCompare(b.name)})return newarr}
17. limitTo获取指定长度的数组
    * {{str|limitTo:10}}
    * 过滤器中使用其他的过滤器
        * app.filter($)
#nodejs http-server
1. npm install  http-server -g
    * 进入需要开启服务器模式的目录
    * 运行http-server
#apple提醒事项
1. 运行http-server
2. 模块化
    * index.js 主要配置
    * 指令.js
    * controller.js
    * filter.js
#iCloud
#Angularjs服务
1. 作用：
    * 对外提供某个特定的功能，如消息服务 文件压缩服务
    * 主要功能是为了实现应用的功能提供数据和对象
2. 数据从哪里来
    * 控制器只会在需要的时候创建 ，在不需要的时候就会销毁，这就意味着控制器无法保存数据，
    * 服务的本质：
        1. 和控制器捆绑在一起的可替换对象
        2. 通过这些对象提供了在应用整个生命周期都可以保存数据的方法
        3. 页面重载和刷新页面时，数据不会被清除，与加载之前保持一致
3. ng的服务
    * 单例对象或函数（对外提供特定功能）
    * 服务是一个单例（每个应用中只会实例化一次）
    * 服务能够提供在应用生命周期内保持数据的方法（依赖注入），并保持数据一致
    * 常用服务有：$scope $filter $rootscope
4. factory(name,fun)有两个参数
    * name(string)
    * fun(){}
#
1. 事件戳是什么？
    * var time=new date()
    * time.getTime()
    * 时间戳就是1970年1月1日到现在所经历的毫秒数
2. icloud中删除所有数据之后就会出现报错、添加失败？
    * 在getdata()中return加了一条默认数据
    * 删除时应至少留一条
3. 失去焦点保存一条事件项目
4. 指令
    * angularjs中<a href=''></a> 元素指令   和我们之前所认识的a标签有区别  href中什么也不添时不刷新页面
    * ng-attr-id='{{a}}'  给标签添加一个id
    * 属性指令
        * <html ng-app='' ng-style='' ng-class=''>
    * 组件指令
        * a、form、input、 select、 script、 textarea
    * 使用指令时，它的名字有多中形式
        1. 作为标签的属性
            * <span my-dir='exp'></span>
        2. 作为标签
            * <my-dir></my-dir>
        3. 作为标签类属性值（不常用）
        4. 作为注释（不常用）
5. 自定义指令
    * 格式
        * 模块.directive('自定义指令名称'function(){return{}) return返回的是对象
    * return返回对象中的参数 restrict(可选) restrict:string
        1. 取值有E（元素）A（属性）C（类名）M（注释）
        2. 默认情况：E A
    * return返回对象中的参数 template 可以看做是模板  把内容放入模板中
        * `template:'<h1>你好</h1>'`（以下两种写法看起来更好一些）
            1. ‘’中的模板（标签太多时）可以使用\换行
            2. ``"<div>"+``
            3.       "<h1>"您好"</h1>"+
            4.      "<p>"内容部分"</p>"+
            5.  `"</div>"`
    * return返回对象中的参数 replace 注释指令必须要有这个
        1. 替换外部结构
        2. replace:true
        3. 默认：false 不替换 直接添加
    * return返回对象中的参数 templateUrl
        1. templateUrl:'文件路径'
        2. 必须是服务器环境
        3. templateUrl和replace只能出现一个,同时出现的话，自定义标签被替换
    * return返回对象中的参数 scope(可选) 默认false
        * scope:false
        1. 改变作用域
        2. false 当前指令和父元素共用一个作用域
        3. true 表示继承父作用域 并创建自己的作用域（子作用域）
        4. {}创建一个全新的作用域（独立作用域）
            * 指令的作用域与外部作用域没有任何关系
            * 绑定策略
                1. @ 让隔离作用域和DOM绑定
                    * {t:'@d'}
                    1. d指的是外部的属性
                    2. t可以随便
                    3. 传的就是@后面的东西
                    4. 单向的数据流
                2. =
                    * {t:'=val'}
                    1. =认为传的是变量
                    2. 可以进行双向数据绑定
                3. & 调用父级中的函数、
                    * {aa:'fn'}
    * return返回对象中的参数 controller
        * 两种写法(都是给绑定一个控制器)
            1. controller:'控制器名'
            2. controller:function($scope){}
    * return返回对象中的参数 transclude
        1. 布尔值或是字符’element‘ 默认值是false
        2. 提取包含在指令那个元素里面的内容，放回指令模板中标记的位置(通常是ng-transclude标记的地方)
    * return返回对象中的参数 link 操作DOM
        * {link:function(scope,element,attr){}
        * 有三种写法
            1. 原生
            2. angular.element()
            3. jquery
##任务
1. 自动轮播
2. 选项卡
#单页面应用（spa）
* 必须要有的一个功能就是页面跳转
* 路由：通过不同的url请求不同的数据
* 好处
    1. 用户体验好
    2. 使用效果和使用本地应用一样
1. ng-route
    1. 安装
        * angularjs中给我们提供了路由这个插件 npm安装路由
        * npm install angular-route
            * 注意：两个js版本要尽可能的接近
                1. angular.js 1.5.0
                2. angular-route.min.js 1.5
        * angular.org  官网下载也可以
        * CDN上安装也可以
    2. 使用
        1. 先引用 `<script src='ng-route.js'></script>`
        2. `app.module('app',['ngRoute'])`
    3. 使用到的指令.函数
        * html中操作
            1. ng-view
                * 指定页面中的那一块被擦除
                * 是由ngRoute模块提供的一个特殊指令，它的独特作用是在HTML中给$route模版内容占用
        * js中操作
            1. config()
                * `app.config(['$routeProvider',function($routeProvider){
                    $routeProvider.when('/',{
                        template:'',
                        controller:'home'
                    })
                }])`或是去掉中括号只用function
                * ` app.controller('home',function($scope){
                })`
                * when()
                    * $routeProvider.when(path,route)
                    * when()中有两个参数path和route
                        1. when('/',fn)中/代表首页 /aa代表其他页
                        2. when('/list:name',fn)
    4. 思路
        1. 下载angular-route.js
        2. 引入js    angular.js   angular-route.js
        3. 创建一个controller.js  (写控制器的)
        4. 在index.html中创建模块，var  app=angular.module('app',['ngRoute','你自己在controller中创建的模块'])
        5. 书写路由
            app.config(['$routeProvider',function($r){
                $r.when('/',{templateUrl:'',controller:''
                }).when('/news',{templateUrl:'',controller:''})
            }])
        6. 添加链接
            <a href="#/"></a>
        7. 那么对应页面的样式应该怎么添加
#知乎
1. 跨域问题(文件代理来解决这个问题)
    * 使用php.get()
        1.写一个php文件api.php

2. index.js
3. controller.js
4. 解决防盗链问题
    * meta标签<meta name='referrer' content='never'>
5. show.html
6. show控制器
7. index-list.html
    * <a href='#show/{{v.url}}'></a>
    * ng-bind-html="data.body" 来解决show.html中获取的内容
        * 要引入一个js  angular-sanitize.min.js 放在jquery下面
        * 还要注入这个js   和route.js一样
8. 获取最新消息
    * 首页显示的列表内容
    * id 3892357
9. 详情页
    * url id3892357
10. 主题列表
    * http//
11. 主题中内容列表
