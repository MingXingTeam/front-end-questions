#前端工作面试问题和答案
**备注：** 本 repo 记录了我做过的所有前端面试题的问题和答案。供以后找工作参考、以及作为前端知识点的练习和总结。

## <a name='toc'>目录</a>

1. [常见问题](#general)
1. [HTML 相关问题](#html) 
1. [CSS 相关问题](#css)
1. [JS 相关问题](#js)
1. [jQuery 相关问题](#jquery)
1. [正则表达式 相关问题](#reg)
1. [设计模式 相关问题](#pattern)

####[[⬆]](#toc) <a name='general'>常见问题</a>

* 对你参与的任何项目或者工作做一个总结，并阐述最难的部分以及最有趣的部分

* 为什么你想在xx公司工作？(内涵：是否对技术有激情 对公司的兴趣)

    * 我的记忆里我一直在用xx公司的产品，然后我对xx公司创造了这么多广泛而优秀

的产品而感到惊奇。比如说我...

* 你的弱点？

    * Sometimes, I don’t have a very good 
    attention to detail While that’s good because it lets me execute quickly, it also means 
    that I sometimes make careless mistakes Because of that, I make sure to always have 
    someone else double check my work 

* 当问到最具挑战的部分的时候？

    * 不要说你要学很多语言和技术。这是一种逃避的答案，这好像告诉面试者没有什么是真的困难的。
    


####[[⬆]](#toc) <a name='html'>常见问题</a>
####[[⬆]](#toc) <a name='css'>CSS 相关问题</a>

* 写出下列代码在各个浏览器中的颜色值？
    
    ```CSS
    background:  red;
    _background: green;
    *background: blue;
    background:  black\9;
    ```
* 添加些CSS让其水平垂直居中

    ```html
    <div style="____________">xxx</div>
    ```
    
* 如下代码，在空白处填写代码，其点击时，前景色为白色，背景色为黑色。

    ```html
    <div onclick="_______________">xxxxx</div>
    ```
* 自适应布局

    * 关于左右自适应的，不低于10种解决方案，还要看dom结构要求是并列还是嵌套，是否允许有父级元素，是否允许使用CSS3，是否有背景色，是否要两列等高，等等

    * 而关于自适应高度的解决方案就略少一些，大致也是靠，CSS3的calc属性，内padding，绝对定位后拉伸，动态js计算等等解决方案，同样也是要看应用场景能用哪个
    
* 移动端自适应

    * 2倍屏，3倍屏的自适应

* 盒模型

    * margin, border, padding组成
    * margin是外边距，border是边框，padding是内边距。
    * 块状元素，行内元素
        * 块状元素占据一行，比如p, div, h2等
        * 行内元素又有：inline-block inline。span、a是inline。inline-block可以设置宽高和margin，padding，border；inline设置宽高无效，padding，margin左右有效，上下无效，border是上面border无效。
    * IE的盒模型有点区别
    * margin不计入盒模型宽和高, html5的话，如果是box-sizing:border-box则padding和border计入宽高，为content－box不计入宽高
   
    

####[[⬆]](#toc) <a name='html'>HTML 相关问题</a>

* 路由的实现原理？



####[[⬆]](#toc) <a name='js'>JS 相关问题</a>

* JS基本数据类型

    * bool, string, number, null, undefined, object, array

* 数组有哪些方法？

    * shift, unshift, slice, splice, push, pop, map
    * slice是取数组的一部分
    * splice是删除数组的某些元素，返回新的数组
    * push是添加元素，相当于入栈
    * pop是出栈
    * map是遍历数组，回调是有数组的index
    
* alert(1&&2) 输出什么？ 2
* 写出下面代码的输出值：

    ```javascript
	var obj = {
		a: 1,
		b: function() {
			console.log(this.a);
		}	
	};

	var a = 2;
	var objb = obj.b;

	obj.b();
	objb();
	obj.b.call(window);

	```
* 写出下面代码的输出值？

	```javascript
	function A() {
	}
	function B(a) {
		this.a = a;
	}
	function C(a) {
		if(a) {
			this.a = a;
		}
	}

	A.prototype.a = 1;
	B.prototype.a = 1;
	C.prototype.a = 1;

	console.log(new A());
	console.log(new B());
	console.log(new C(2));
	```

* 写出下面代码的输出值

	```javascript
	var a = 1;
	function b() {
		var a = 2;
		function c() {
			console.log(a);
		}
		return c;
	}

	b()();
	```

* 书写代码，点击时从1分钟开始，每秒递减到0
    
    ```html
    <div onclick="test()">xxx</div>
    ```

* 简述在IE下mouseover和mouseenter的区别

* 手写事件模型和事件代理/委托

    * 捕获、目标、冒泡 低版本IE不支持捕获阶段
    
    * IE和w3c不同绑定事件解绑事件的方法有什么区别，参数分别是什么，以及事件对象e有什么区别
    
    * 事件代理/委托的原理以及优缺点
        
        * 原理：事件冒泡机制  
        * 优点：节省内存占用，减少事件注册; 动态内容绑定很方便
        * 所有代理委托给document或body的坏处：可能出现事件误判
    * 手写原生JS实现事件代理并要兼容浏览器(考核事件对象e和e在IE对应的属性名：target, currentTarget, IE下是srcElement和this)
    * 实现事件模型：写一个类或是一个模块，有两个函数 一个绑定一个trigger。分别实现绑定事件和触发事件。(对某一个时间名称绑定多个事件响应函数，然后触发这个时间名称时触发对应的函数)
    
        * 触发响应函数的上下文，触发响应函数的参数列表应该是什么，把arguments转为数组
        * 事件广播dispatchEvent
        
* 前端性能优化 (懂则讲 不懂略过)

    * 网络性能优化；加快访问速度；浏览器并行加载数量；原生JS异步载入；CDN加速的原理；静态资源发布到多个域名服务器(发布后这些静态字段的url路径如何批量改)；项目打包工具；css打包后的相对路径怎么转绝对路径；项目模块依赖管理工具；cookie优化

* 闭包原理及应用

    [闭包测试题目](http://www.cnblogs.com/xxcanghai/p/4991870.html)
    
* 手写Function.bind函数

    * 保持函数的this指向
    * 保持函数的所有参数都传递到目标函数
    * 保持函数的返回值
    
    ```javascript
    if(!Function.prototype.bind) {
        Function.prototype.bind = function(oThis) {
            if(typeof this !== 'Function') {
                throw new TypeError("Function.prototype.bind - what is trying to be bound is not callable");
            }
            
            var aArgs = Array.prototype.slice.call(arguments, 1),
                fToBind = this,
                fNOP = function() {},
                fBound = function() {
                    return fToBound.apply(
                        this instanceof fNOP?this:oThis || this, 
                        aArgs.concat(Array.prototype.slice.call(arguments));
                };
                
            fNOP.prototype = this.prototype;
            fBound.prototype = new fNOP();
            
            return fBound;
        }
    }
    ```

* 手写数组快速排序/去重

* JS定义提升

    [测试题目](http://www.cnblogs.com/xxcanghai/p/5189353.html)

* 跨域

    * iframe跨域：   
    [文章1](http://www.cnblogs.com/rainman/archive/2011/02/20/1959325.html)  
    [文章2](http://www.cnblogs.com/scottckt/archive/2011/11/12/2246531.html)  
    [文章3](http://www.cnblogs.com/cat3/p/archive/2011/06/15/2081559.html)  
    * 跨全域请求： JSONP,Access Control,服务器代理

* 将url的查询参数解析成字典对象

    * 用正则实现 如果是这种格式怎么弄？ /param1/param2/
    
    ```javascript
    function getQueryObject(url) {
        url = url == null ? window.location.href : url;
        var search = url.substring(url.lastIndexOf("?") + 1);
        var obj = {};
        var reg = /([^?&=]+)=([^?&=]*)/g;
        search.replace(reg, function (rs, $1, $2) {
            var name = decodeURIComponent($1);
            var val = decodeURIComponent($2);                
            val = String(val);
            obj[name] = val;
            return rs;
        });
        return obj;
    }
    ```

* 函数节流

    * 场景：常见的场景，如网页滚动时，经常会有滚动到哪时做什么样的动画效果，遂要注册onscroll事件，如何减少触发次数，到达优化性能，同时又满足效果要求不卡顿，一个是优化事件内代码，减少代码量，二就是做函数节流
    
    [文章](http://www.alloyteam.com/2012/11/javascript-throttle/)
    

####[[⬆]](#toc) <a name='jquery'>jquery 相关问题</a>
####[[⬆]](#toc) <a name='reg'>正则表达式 相关问题</a>

* 正则表达式匹配，开头为11N，12N或1NNN，后面是7-8个数字的电话号码。

####[[⬆]](#toc) <a name='pattern'>设计模式 相关问题</a>

* 观察者模式，职责链模式，工厂模式(UI组件封装时用到)


=================

### 其他

* 简历上要展示两个方面：是否聪明；是否能写代码

*   项目展示：2 - 4 most significant projects
    
    1、什么语言
    
    2、个人项目还是团队
    
    3、关于什么的内容

        Accomplished X by implementing Y which led 
        to Z 
        show what you did, how you did it, and what the results were Ideally, you 
        
        should try 
        to make the results “measurable” somehow。
        Go out and get project experience；

* 简历上不要包含个人信息：比如年龄、婚姻状态、国籍等




