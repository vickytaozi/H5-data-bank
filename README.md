# vicky123
学习H5的过程如同龟兔赛跑的过程
##Requirejs  
引人requirejs注意点：
1.路径，配置接口文件config( )方法
2.按需加载
3.不能保证哪个先加载的情况，使用嵌套
模块定义规范，必须参照
4.当我们没有引用入口地址时，默认为baseUrl:的为data-main
RequireJS常用的方法：
1.Requirejs.config
2.requirejs
3.define

步骤：
1.首先是下载（http://www.requirejs.cn/docs/download.html）引人require.js 文件
再把入口文件data-main='' js/main'' 这里不需要.js
代码：
<script src ="js/require.js" data-main="js/main"></script>
 2.创建main.js 文件，保留在js目录下
里面打代码：
requirejs.config({
	Paths: {
		Jquery:'jquery-1.11.3.min'
	}
});

Requirejs(['jquery'],function($) {
	测试代码:
	$('baby').css('background-color','red');
	
});

3.创建一个模块,将一个个功能定义成一个模块, 文件名为validata.js

Define(['jquery'],function($){
	Return{
		isEqual:function(str,str2){
			Return str ===str2;
		}
	}

});
4.回到main.js文件，引人刚才创建的功能模块validata.js

requirejs.config({
	Paths: {
		Jquery:'jquery-1.11.3.min'
	}
});

Requirejs(['jquery','validate'],function($,validate) {
	$('baby').css('background-color','red');
	Console.log(validate.isEqual(1,2));
	 最后返回结果：false
});





使用shim 插件
配置一个shim 的文件
Shim:{
	Exports:"jQuery.fn.sroll"
}


模块化开发的优点：
避免命名冲突
更好的依赖处理
按需加载
面向对象编程
AMD：异步模块定义规范（预加载）
AMD规范：
Asynchronous Moduel   
CMD：通用模块定义规范（延迟加载）
sea.js  模块代码
  

