前端页面分为三部分：结构层（html 代码），表示层（css 层叠样式表），行为层（javascript 脚本）

css 层叠样式表分为：1.外部样式 2.内部样式 3.内联样式（行内样式）

pc 端文字字号最小是 12，默认是 16
页面中的栏目标题尽量用 h3

-moz-transform:rotate(7deg); //-moz 代表火狐内核识别码
-webkit-transform:rotate(7deg); //-webkit 代表谷歌内核识别码
-o-transform:rotate(7deg); //-o 代表欧朋【opera】内核识别码

标签
article 定义文章  
aside 定义页面内容之外的内容  
section 定义 section 部分  
nav 定义导航链接  
div 可以理解为盒子模型  
h1-6 标题，字体依次是由大到小  
br / 强制换行  
p 段落  
i 倾斜  
b 加粗  
em 强调  
strong 强烈强调  
span 特殊  
sub 下角标  
sup 上角标  
ul 无序列表  
li 列表项  
form 表单  
Textarea 文本域  
Input 输入框  
选择器：  
.n{color:red;} 类选择器  
#n{color:blue;} id 选择器  
.t span{color:yellow;} 后代选择器  
span+span{color:cyan;} 相邻兄弟选择器  
.t > span{color:hotpink;} 子集选择器  
li:nth-child nth 选择器  
odd 奇数  
even 偶数  
:after 选择器在被选元素的内容后面插入内容。请使用 content 属性来指定要插入的内容。

Css 元素  
float 浮动  
margin：0 auto 水平居中  
line-height 垂直居中  
margin-top 上边距  
border-top 上边框  
border-bottom 下边框  
solid 实线  
background-image:url(); 背景图  
background-repeat：no-repeat/repeat-x/repeat-y 背景重复:不重复/水平重复/纵向重复  
background-position 背景图位置  
background-size x（横向）y（纵向） 背景图尺寸  
font-family 字体  
font-weight:normal/bold/bolder 字体加粗：正常/定义粗体字符/定义更粗的字符/ 定义更细的字符 100-900 定义由细到粗的字符。400 等同于 normal，而 700 等同于 blod  
sans-serif 无衬线  
overflow:hidden 溢出：隐藏  
Overflow:auto 溢出部分可变为滚动条  
line-height 行高：固定高度/倍数  
text-align:center/left/right 文本居中/居左/居右  
front-style：oblique 字体风格：斜体  
word-spacing 词间距（根据空格）  
letter-spacing 字间距  
text-indent 首行缩进  
ctrl+y 恢复撤销  
cover 把背景图扩展至足够大  
Contain 在 div 里把图片等比缩放  
a href 网址；路径  
list-style:none/circle/square/disc 去掉列表符号/空心圆/方块/实心圆（默认的）  
list-style-image：url 用图片替代列表符号:（‘路径’）  
padding 内间距  
text-decoration:none/underline/line-through/overline 去掉下划线/下划线/中划线/上划线 hover 鼠标经过  
display:block 转换为块元素  
margin：50px 100px 20px 2 个数的时候:上下 左右  
3 个数的 时候：上 左右 下  
4 个 数的时候：顺时针（上、右、下、左）

```
<a href="网址" target="blank">前往</a>  
```

a:link 未访问的链接  
a:visited 已访问的链接  
a:hover 鼠标移动到链接上  
a:active 选定的链接  
\_blank 在新窗口中打开被链接文档  
display:block/inline/inline-block/none 转换为：块/行内/行状块/隐藏  
clear{clear:both;} 清除浮动

<div class="clear"></div>     						在最后一个浮动元素后加空标签  
dashed                        					虚线  
position：relative   		 						相对定位  
z-index       			 						层叠  
position:absolute       	 						绝对定位  
position:fixed                 	 				固定定位  
boder-radius                     					圆角  
text-shadow:h-shadow/v-shadow/blur/color			文本阴影效果/必需。水平阴影的位置，允许负值。/必需。垂直阴影的位置，允许负值。/可选。模糊的距离/可选。阴影的颜色  
linear-gradient  线性渐变  to right 从左到右渐变  to bottom right   往右下方渐变角度定位（deg代表度数 ，颜色）  
Focus											焦点  
Box-shadow：h-shadow/v-shadow/blur/spread/color/inset
给框添加一个货多个阴影:必需。水平阴影的位置，允许负值。/必需。垂直阴影的位置，允许负值。/可选。模糊的距离/可选。阴影的尺寸。/阴影的颜色/将外部阴影改为内部阴影。  
Cursor     光标。    Default  默认光标；auto  默认。浏览器设置的光标；pointer 光标		呈现为指示链接的指针（一只手）  
Background-origin：padding-box         背景图相对于	内边距框来定位  
Background-origin：border-box 			背景图相对于边框盒来定位  
Background-origin：content-box          背景图相对于内容框来定位  
Background-clip						规定背景的绘制区域  
Opacity								透明  
Vertical-align                  设置元素的垂直对齐方式。  
dotted							点状边框  
max-width						把img图片放到足够大  
引用字体的格式：  
```
@font-face{
			font-family: 起的名字;
			src:url('../fonts/BebasNeue-webfont.eot'),
				url('../fonts/BebasNeue-webfont.ttf'),
				url('../fonts/BebasNeue-webfont.moff'),
				url('../fonts/BebasNeue-webfont.svg');
		}

````
table								块级表格  
table-row							表格中的行  
table-cell							表格中的列
calc								计算  



表单元素
input type="text"        	 		用户名  
input type=“password” 	 			密码  
input type="radio" name="#"     	与其他名称一致时，它就是单选按钮  
input type="checkbox"            	多选  
checked disabled                 	已选；必选  
input type="submit"              	提交  
input type="button"	value=””	 	空白按钮 、按钮的内容  
```<Textarea rows=""  cols="" >```	文本域 （默认的行）（默认的字符）  
select name="" id=""             	表单中的下拉菜单  
	<option>   <option/>    		表单中的下拉菜单项  

<label for=”名字”>  
input type=“名字” id=“起的名字”  
</label>									在 label 元素内点击文本，就会触发此控件。  
input outline					轮廓，边框  






块元素：（1 块级元素各占一行，是垂直方向布局的。  2 高度，行高以及外边距和内边距
都可控制；  3 默认宽度始终是与浏览器宽度一样，与内容无关。 4 它可以容纳内联元素
和其他块元素）  

行内元素：（1 行内元素会再一条直线上，是在同一水平线布局的。2 高，行高及外边距和
内边距部分可改变； 3 宽度只与内容有关； 4 行内元素只能容纳文本或者其他行内元素）  






快捷键
Alt+shift+2				同时打开两个窗口




2D
transfrom				向2D或3D转换
translate					位移
rotate					旋转。允许负值，元素将逆时针旋转
scale					缩放
skew					元素翻转给定的角度
matrix					矩阵
transition					过渡属性的简写
transition-property			规定过渡的css属性名称
transition-duration			过渡效果花费的时间
transition-timing-function	过渡效果的时间曲线
transition-delay			过渡效果何时开始
linear					以相同速度开始至结束的过渡效果
ease						慢速开始，然后变快，，然后慢速结束的过渡效果
ease-in					以慢速开始的过渡效果
ease-out					以慢速结束的过渡效果
ease-in-out				以慢速开始和结束的过渡效果

animation				所有动画属性的简写
animation-name			规定@keyframes动画的名称
animation-duration			规定动画完成一个周期所花费的秒或毫秒
animation-timing-function	规定动画的速度曲线
animation-delay			规定动画何时开始
animation-iteration-count	规定动画被播放的次数
animation-iteration-count：infinite	规定动画应该无限次播放
animation-direction		规定动画是否在下一周期逆向播放
animation-direction:alternate		规定动画应该反向播放
animation-play-state		规定动画是否正在运行或暂停
animation-fill-mode		规定对象动画时间之外的状态
animation-fill-mode:forwards			当动画完成后，保持最后一个属性值（在最后一个									关键帧中定义）

响应式
目标元素÷上下文元素（父级）=百分比
媒体查询：@media screen and (min-width: 768px) and (max-width: 968px){
			body{background-color:red;}
		}
兼容
CSS hack主要有三种：IE条件注释法、选择器前缀法、CSS属性前缀法。
（lt 是小于，！是不等与 ，gt是大于，lte是小于等于，gte是不小于）

IE条件注释法
 例：<!--[if IE 8]>
<p>Welcome to Internet Explorer 8.</p>
<![endif]-->
注意：ie10及以上注释法失效。

CSS属性前缀法
body{
	background:red;
	background:blue\0/;	ie8专属HACK
	background:blue\9;		IE6/IE7/IE8/IE9/IE10都生效
	background:blue\0;		ie8及以上
	background:blue\9\0;	ie9  ie10
	_background:blue;		ie6
	*background:blue;		ie6&7
｝
!important		提升优先级（只在IE6里面管用）



选择器前缀法
*html 														*前缀只对IE6生效
*+html 													*+前缀只对IE7生效
@media screen\9{...}										只对IE6/7生效
@media \0screen {body { background: red; }}				只对IE8有效
@media \0screen\,screen\9{body { background: blue; }}		只对IE6/7/8有效
@media screen\0 {body { background: green; }} 				只对IE8/9/10有效
@media screen and (min-width:0\0) {body { background: gray; }} 只对IE9/10有效
@media screen and (-ms-high-contrast: active), (-ms-high-contrast: none) {body      { background: orange; }} 								只对IE10 IE11有效等等

H5标签ie8 不识别问题
1.css：article,aside,dialog,footer,header,section,footer,nav,figure,menu{display:block;}
2.Head下面添加：
<!--[if lt IE 9]>
<script>
   (function() {
     if (!
     /*@cc_on!@*/
     0) return;
     var e = "abbr, article, aside, audio, canvas, datalist, details, dialog, eventsource, figure, footer, header, hgroup, mark, menu, meter, nav, output, progress, section, time, video".split(', ');
     var i= e.length;
     while (i--){
         document.createElement(e[i])
     }
})()
</script>
<![endif]-->
IE6bug汇总
双边距：一个div盒子如果设置了margin，并且该div设置了float浮动，那么在IE6下便会产生双边距问题：如果设置 float:left 那么左边距会是原来margin的两倍；如果是float:right，那么右边距会是原来margin的两倍。      解决办法：_display: inline
3像素：3像素bug是IE6的一个著名的bug，当浮动元素与非浮动元素相邻时，这个3像素的Bug就会	出现。 在浮动元素上加上_margin-right:-3px;
微型高度这个BUG的产生原因很简单，IE不允许元件的高度小于字体的高度，所以，下面的fix是设置上字体大小。解决方案一{font-size:0px;} 解决方案二{overflow:hidden;}(最佳)
绝对定位：在IE6下面 position:absolute的绝对定位层前面紧邻的那个层如果有用到“float” css浮动属性会导致这个绝对定位层无法显示解决办法就是在这个绝对定位浮动层前面插入一个清除浮动的层（或者空div）
Png透明：img和background都有不同的解决办法但是不能同时兼容因此引入一个js来解决，
!–[if IE 6]><script type=”text/javascript” src=”js/DD_belatedPNG_0.0.8a-min01.js”></script>
	<script type=”text/javascript”>
	DD_belatedPNG.fix(‘选择器名称  , 应用类型（属性名称或者是元素名称）’);
	</script>
	<![endif]–>
IE6不识别最大最小宽高的问题。
max-width:1000px;
_width:expression((document.documentElement.clientWidth||document.body.clientWidth)<1000?"1000px":"");
overflow:hidden;

min-width:1000px;
	_width:expression((document.documentElement.clientWidth||document.body.clientWidth)>1000?"1	000px":"");

max-width:620px;
	min-width:1px;
	_width:expression(this.scrollWidth > 620 ? "620px":(this.scrollWidth < 1? "1px":"auto"));

max-height:1000px;
	_height:expression((document.documentElement.clientHeight||document.body.clientHeight)<1000?"	1000px":"");
	overflow:hidden;

min-height:1000px;
	_height:expression((document.documentElement.clientHeight||document.body.clientHeight)>1000?"	1000px":"");

Max-Height:620px;
	Min-Height:40px;
	_height:expression(this.scrollHeight > 620 ? "620px":(this.scrollHeight < 40 ? "40px":"auto"));


360浏览器
<meta name="renderer" content="webkit">
<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
<!-- E=edge：保持使用最高级别模式显示内容；

chrome=1：谷歌的外挂插件Google Chrome Frame（谷歌内嵌浏览器框架GCF），使用IE浏览网页时实际上是使用Chrome浏览器内核渲染，最低支持IE6，但前提是客户端已经安装GCF。 -->



Chrome谷歌浏览器下不支持css字体小于12px的解决办法
-webkit-transform : scale()
@media screen and (-webkit-min-device-pixel-ratio:0) {   }chrome /safari
 @media screen and (-moz-images-in-menus:0) {   }ff   或者css后缀！important
@media all and (min-width: 0px){  \0}opera



移动端兼容
1	fixed元素无法点击
场景：父元素设置position: fixed;
子元素设置position: absolute;
此时，如果父元素/子元素还设置了overflow: hidden 则出现“父元素遮挡该子元素“的bug。
视觉(view)层并没有出现遮挡，只是无法触发绑定在该子元素上的事件。可理解为：「看到点不到」。
补充： 页面往下滚动，触发position: fixed;的特性时，才会出现这个bug，在最顶不会出现。
解决办法： 把父元素和子元素的overflow: hidden去掉。
2	场景：<video>标签的父元素(祖辈元素)设置transform样式后，<video>标签会脱离文档流。
解决方案：不使用transform属性。translate用top、margin等属性替代。<video>总是在前
3	textarea这个标签，具有默认样式
-webkit-appearance: none;? ?通过这个属性可以取消；
4	拨打手机直接如下
<a href="tel:15677776767">点击拨打15677776767</a>
     <a href="tel:4008106999,1034">400-810-6999 转 1034</a>
5	圆角bug/：某些Android手机圆角失效
background-clip: padding-box;
6	通过transform进行skew变形，rotate旋转会造成出现锯齿现象
-webkit-transform: rotate(-4deg) skew(10deg) translateZ(0);
	transform: rotate(-4deg) skew(10deg) translateZ(0);
	outline: 1px solid rgba(255,255,255,0)
7	个人建议有些动画用transition来做尽量不要用animation(常用循环动画)
必要时还要打开其渲染3d功能。在全局样式中进行设置如下样式：
-webkit-transform-style:preserve-3d;
-webkit-backface-visibility:hidden;
-webkit-transform:translate3d(0,0,0)




jQuery
jQuery使用
1.下载  min.js（压缩版）     .js非压缩版
2.引入到html文件，使用script（src属性，写路径）标签，位置：body内部最后边
例：<script src=””></script>
3.使用  在script标签中使用，但这个标签和引入标签不相同
例：<script>
		$(".button").click(function(){
			$(".wrap").css("background-color","blue")
		})
	</script>


js代码：严格区分大小写  非js语法要用“”或‘’包裹（字符串）
选择器 xxx：first 选择所有xxx中的第一个
选择器 xxx：last 选择所有xxx中的最后一个
选择器 xxx：eq（数值n） 选择所有xxx中下标为n的那个

.css()		改变样式
.attr()		改变属性
阻止a链接跳转：在事件最后面写return false
$(this)		触发事件的这个元素
event		事件对象
event.preventDefault()并且在function加（event）				阻止事件默认跳转
event.pageX		event.pageY			鼠标距离浏览器窗口的偏移位置


检测代码的方式：
Alert			弹出事件提醒
Console.log（）	控制台输出

快捷键：ctrl+shift+D  快速复制光标前的这一行代码
ctrl+shift+上下键    交换上下行位置

变量	存储值的容器
1.声明	  var 名（驼峰命名 第二个首字母大写）
2.存储	 用赋值操作 变量=值
3.使用  直接用变量名 不用加引号

.parent()			查找父级
xx.index()			获取xx的索引值
xx.siblings()		查找xx的其他兄弟元素
xx.find()		查找后代
xx.parents()				查找祖先
xx.children()				查找子级
.next()					同级的下一个兄弟
.width()	.height()			获取或设置宽高
注：括号里都可以加选择器
xx.addclass(class名)			给xx追加class名
xx.removeclass(class名)			给xx删除class名
.toggleClass（‘class名’）		按钮开关
.hover(function(){滑入}，function(){滑出})
.mouseenter()滑入			.mouseleave()滑出


不让a标签里的#跳转时，可以把#替换成“javascript：void（0）”和在js最后放return false意思相同。
slideUp上卷			slideDown下拉			slideToggle上卷下拉的切换
hide	 消失			show 出现				toggle 切换
fadeIn淡入（毫秒数）			fadeOut淡出（毫秒数）
fadeToggle 淡入淡出的切换

JQ动画
.animate（｛样式的改变｝，500，functiion（）｛回调｝）     自定义动画
注：只有body或html才有scrollTop样式，所以给scrollTop写动画要绑定在$（“body,html”）上

Mousemove（function（）｛｝）					鼠标移动事件
hasClass（“class名”）				检测元素中是否有该class名，有的话控制台返回										true，没有则返回false
if（）判断条件成立	else 判断失败
表单元素type属性选择器：  比如 input：button			input：text
获取文本：表单元素用.val（） 除表单元素之外的用.text（）
修改文本：表单元素用.val（xx）除表单元素之外的用.text（xx）
创建标签：$（“<标签名>”）
添加标签：a.append（b）		将b添加到a内部（子级），位置最后一个
			  a.prepend（b）		将b添加到a内部（子级），位置第一个
			  a.before（b）		将b添加到a的前面（同级），位置前一个兄弟
			  a.after（b）		将b添加到a的后面（同级），位置后一个兄弟
val“”			空字符串
a.trim（）			将a这个值的左右空白符删除
a.clone（）			克隆一个一模一样的a
a.remove（）			删除整个a元素，包括里面的内容
.prop（要选的东西）				是否选中
xx.each（function()｛要做的事｝）遍历xx集合中的所有元素，依次做function里面的事
select表单元素	.val（）获取被选中的option的value值
.change				给checkbox绑定点击事件时，使用change
.keydown				键盘按下
.keyup				键盘弹起
.ldypress				按键盘
.focus				获得焦点
.blur					失去焦点
event.which			获取所按键盘的code码	13是代表回车
$（window）			代表浏览器窗口
xx.trigger（“事件名称”）			执行xx的事件内所有的操作
滚动条事件  窗口$（window）.scroll（）  窗口的滚动条事件
$（window）.scrollTop（）			获取窗口滚动条距顶部的距离
.offset（）					获取元素相对文档的坐标
.offset（）.top				获取元素相对文档的纵坐标
.offset（）.left				获取元素相对文档的横坐标
xx.length						获取xx这个集合元素中的个数
	例：console.log（$（“ul>li”）.length）
.on								可以绑定多个事件
event						事件对象
````
