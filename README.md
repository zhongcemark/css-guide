# css-guide
team of zhongce mark's css guide book
***

1、对于网站非通用元素，如果样式简单(1~2个属性)，对其分离并使用面向属性的命名方法：千万不要对网站通用的元素进行分离。
2、精简高效CSS命名之“三无原则”；无ID，无层级，无标签，减少层级，避免过度修饰，如：
```html
#test .test{}， ul.test{}，#test ul{} ：都不推荐 			
div.promo 			
ul.nav li a{} -> .nav a{}
```

3、重复的属性不要放在一起，会增加渲染的时间，如：
很多网站CSS模块都组队放在一个CSS文件中，比方说你有10个CSS模块，每个模块都有一个.module_a a{} .module_b a{} ...的CSS命名，如：
```html
.module_a a{}的时候，页面上，所有的a标签扫一遍；
.module_b a{}的时候，页面上，所有的a标签扫一遍；
.module_c a{}的时候，页面上，所有的a标签扫一遍，恩，这个有效果；
.module_d a{}的时候，页面上，所有的a标签扫一遍；
```

> 扫一遍只要0.3毫秒，你页面要是有100个类似.xxx a{}，那就是300毫秒的渲染	

####组内规范，如：	
#####A、通用属性：
######对于有了ue规范的平台来说，定义标准变量的好处是显而易见的，如：
margin属性：
```css
ma: 0 auto;
m-tiny: 1px;
m-small: 3px;
m-middle: 5px; 
m-big: 8px;
m-bigger: 10px;
m-huge: 20px;
```
		
padding属性：
> 同margin；
		
#####B、前缀，减少冲突概率和：
######1、全局布局使用的class：可以不用前缀，如：
```html
头部：header
尾部：footer
侧栏：sider
内容包裹：mainer/container
核心内容：inner			
导航：nav
子导航：subnav
菜单：menu
子菜单：submenu
```

> 这些变量主要定义框架的布局，如宽度、高度、自适应的大小、背景色、字体大小、对齐方式、
		
######2、通用组件前缀或在多个页面会被用到的类名：
前缀解释：
```html
common
general
special
normal
```

前缀实战：
```css
com-
gen-
spe-
nom-
```
```css
com-mark-page-wrap
com-mark-p-question
com-mark-pq-content
com-mark-pq-choice
com-mark-pq-operate
com-mark-p-instruction
```

#####参考文档：
[参考1](https://github.com/hoosin/lite/blob/master/Standard/%E9%80%9A%E7%94%A8%20CSS%20%E7%AC%94%E8%AE%B0%E3%80%81%E5%BB%BA%E8%AE%AE%E4%B8%8E%E6%8C%87%E5%AF%BC.md)
[参考2](http://www.zhangxinxu.com/wordpress/2010/09/%E7%B2%BE%E7%AE%80%E9%AB%98%E6%95%88%E7%9A%84css%E5%91%BD%E5%90%8D%E5%87%86%E5%88%99%E6%96%B9%E6%B3%95)
[@quenteenfix](http://weibo.com/u/2410897424)
