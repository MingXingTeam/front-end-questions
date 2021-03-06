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
1. [浏览器 相关问题](#browser)

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

    * _ ：IE6支持
    * * : IE6、7支持(IE6不支持!important)
    * \9: 所有IE都支持

* 添加些CSS让其水平垂直居中

    ```html
    <div style="____________">xxx</div>
    ```
    
    * position:absolute;
      top:50%;
      left:50%;
      transform:translate(-25%,-25%);

    * display: flex;
      align-items: center;
      justify-content: center;  

    * height: 90px;
      line-height: 90px;
      margin: 0 auto;

    *文本垂直水平居中：
        div {
          display: table;
          width: 250px;
          height: 100px;
          text-align: center;
        }

        span {
          display: table-cell;
          vertical-align: middle;
        }
    
    *
    
* 如下代码，在空白处填写代码，其点击时，前景色为白色，背景色为黑色。

    ```html
    <div onclick="_______________">xxxxx</div>
    ```

    * !function(me){me.style.cssText='background:black;color:#ffffff'}(this)

* 自适应布局

    * 关于左右自适应的，不低于10种解决方案，还要看dom结构要求是并列还是嵌套，是否允许有父级元素，是否允许使用CSS3，是否有背景色，是否要两列等高，等等

    ```

    ```

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
   
* 什么是BFC?   

    * BFC是指“块级格式上下文”，当一个元素生成BFC的时候，它会有一套渲染规则。
    * BFC现象：在一个BFC中，相邻块级元素的垂直外边距会发生折叠(折叠有一定规则)
    * 生成BFC的方式：浮动元素、绝对定位元素、非块级盒子的块级容器(inline-block, table-cell, table-caption)、overflow值不为visiable的块级盒子。

* 媒体查询？

    * 1px逻辑像素=2^2物理像素
      iPhone4、5、5s分辨率320x568，像素640x1136，@2x
      iPhone6分辨率375x667，像素750x1334，@2x
      iPhone6 Plus分辨率414x736，像素1242x2208，@3x
    * viewport的宽度设置为640然后通过计算window.screen.width/640缩放，font-size设置为125% 刚好是20px；width设置为4rem 刚好为80px
    * 响应式布局一般是改变样式(比如隐藏某些元素，增加新的样式)
    
* 响应式布局
    
    * 媒体查询设置视口断点
    * 流体布局技术：display:inline-block；max-width&min-width；column-width;display:flex;vm(根据可视区域变化);img标签的srcset和imageset适配2倍屏和3倍屏；锁定宽高比(伪类，纵向padding)；矢量图
    

* 等高布局
    
    * margin-bottom:-1000px; padding-bottom: 1000px;
    * display: table; table-layout: fixed; display: table-cell;width: 50%;

* 等宽布局

    * flex-box
    * display: table; table-layout: fixed; display: table-cell;

* rem, em区别？

    * rem是相对跟元素
    * rem是相对父元素

* 什么情况下会重绘和重排？

    * 字体变化、颜色变化、背景图片等变化都会导致重绘。
    * 宽度和高度变化、内容变化、border变化都会导致重排。
    * 重排一定会导致重绘
    * 尽量避免重绘和重排能提高页面性能：比如用cssText代替，style.width等

####[[⬆]](#toc) <a name='html'>HTML 相关问题</a>


####[[⬆]](#toc) <a name='js'>JS 相关问题</a>

* JS基本数据类型

    * boolean, number, null, undefined, object, string,

* 数组有哪些方法？

    * shift, unshift, slice, splice, push, pop, map, sort, forEach, concat
    * shift删除数组的第一个元素，并返回删除的元素(原数组发生改变了)
    * unshift(elem)添加元素到数组头部，并返回新的数组的长度
    * slice(start, end)是取数组的一部分，返回新的数组
    * splice(start, deleteCount, addItem..)是删除数组的某些元素并添加新元素到末尾
    * push是添加元素，相当于入栈
    * pop是出栈
    * map是遍历数组，回调参数是currentValue, index, array

* 字符串有哪些方法？

    * match，replace，search，indexOf, lastIndexOf, split， substring, concat, includes, slice
    * includes:判断一个字符串是否是另一个字符串的串
    * “asdf”.match(//): 匹配正则
    * replace(//,"$1"): 匹配正则并替换
    * slice： 提取字符串的一部分

* 懒加载的实现原理？
    
    * 判断是否在页面显示区域，如果在显示区域则载入图片
    * 页面显示区域(document.innerHeight&document.innerWidth)(getBoundingClientRect()方法)
    * 载入图片：setAttribute("src", src)

* 路由的实现原理？

    * 设置一个对浏览器的地址的监听或者用window.onhashchange(newURL, oldURL)
    * 对每一个hash注册不同的回调函数
    * hash改变时，调用window.history.pushState将路由地址放入参数中。

* 前端模块管理器的实现原理？

    * XMLHttpRequest同步请求文件数据(非跨域，如果跨域用script)
    * 用iFrame的eval执行返回文件数据，并定义access方法(with方法)
    * export方法本质：Object.defineProperty定义get和set方法，再访问host的eval方法

* SessionStorage和LocalStorage

  * SessionStorage是一次会话，浏览器不关闭则一直存在
  * LocalStorage一直存在

* 动态事件绑定实现的原理是？

    * 冒泡

* 怎么实现文件跨域上传？
    * 一般上传文件是form提交(enctype="multipart/form-data")
    * 跨域：服务器代理；jsonp；script标签；cors

* Angular和React的区别，为什么使用Angualr或React，怎么选？

    * Angular比较大，有很多特性，比如Directive, 模板，双向绑定啥的。开发小项目很快，但大项目复杂度大了，因为有很多API会比较难维护。
    * React只专注View层比较轻量，而且它有虚拟DOM的特性（只产生一棵渲染差异树），性能会比较好。

* append和innerHTML的区别？

    * append要找到当前元素，遍历子元素，再拼接；而innerHTML直接替换就行。

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

    * 1
    * 2
    * 2

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

    * { } //why ? A对象本身没有属性，但是如果是A.a 则会打印出1(如果当前对象里没有 则到原型里找a属性)
    * {a: undefined}
    * {a: 2}

* webpack如何调试？

    * source-map。webpack的配置项里有一个dev-tools，配置成eval就行了

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

    * 2

* 书写代码，点击时从1分钟开始，每秒递减到0
    
    ```html
    <div onclick="test()">xxx</div>
    ```

* document.ready和window.onload的区别？

    * ready是DOM树形成时调用，onload是页面所有渲染完成并且资源请求成功后调用。

* 手写事件代理/委托

    * 原理： 绑定事件到父元素，事件冒泡机制

* 手写事件模型

    * addEventListener, removeEventListener, attachEvent, detachEvent
    * event.currentTarget绑定事件的元素， event.target当前被点击的元素(IE下是srcElement和this)
    
* 前端性能优化 (懂则讲 不懂略过)

    * 网络性能优化；加快访问速度；浏览器并行加载数量；原生JS异步载入；CDN加速的原理；静态资源发布到多个域名服务器(发布后这些静态字段的url路径如何批量改)；项目打包工具；css打包后的相对路径怎么转绝对路径；项目模块依赖管理工具；cookie优化

* 闭包原理及应用

    [闭包测试题目](http://www.cnblogs.com/xxcanghai/p/4991870.html)
    
* 手写Function.prototype.bind函数

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

* 手写原生JS实现JSONP跨域

* 手写原生JS实现Ajax

* 

####[[⬆]](#toc) <a name='jquery'>jquery 相关问题</a>
####[[⬆]](#toc) <a name='reg'>正则表达式 相关问题</a>

* 正则表达式匹配，开头为11N，12N或1NNN，后面是7-8个数字的电话号码。

####[[⬆]](#toc) <a name='pattern'>设计模式 相关问题</a>

* 观察者模式，职责链模式，工厂模式(UI组件封装时用到)

####[[⬆]](#toc) <a name='browser'>浏览器 相关问题</a>

* HTTP缓存机制？
    
   

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




