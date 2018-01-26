---
title: css文件分类
---
一般网站分为三个样式文件，分别为reset.css(重置样式)，common.css(公共组件样式)，layout.css(当前页面样式)
##情况一

### reset.css

清除全站所有页面的浏览器默认样式，保证在初始样式在所有浏览器下一致。

### common.css

一般一个网站所有页面头部、底部样式都是一致的，而且很长时间不会有大的改变，改变的大概就是产品、运营的经常需要添加、去掉某些入口的需求，要保证全站所有页面头部一次替换生效，只需要把这些公共部门的样式提取出来，放在common.css文件中，这样既可以一次修改成功，比如翻页、表单（输入框、按钮）等样式也是全站统一的，把这些样式都放到common.css里面，如果哪天所有的按钮样式要变更，一次替换就成功了。

### layout.css

公共组件以外的所有样式都写到这个样式文件里面，并且保证一个页面一个独立样式，页面html和css写法要模块化，保证迅速响应项目频繁的迭代。

##情况二

网站的样式分类也可以只有两个，即reset.css(重置样式)和layout.css(当前页面样式)，不要把什么东西都往组件样式里面塞，有写东西宁愿每个页面重复拷贝也不要塞到组件样式里面去。某一天，你会发现这个组件样式大得让你可怕，而且很多都是无用的。

``` css
@charset "utf-8";
/****** reset 基本样式重置 strat ******/
/* 清除内外边距 ---------- */
html,body{ height: 100%;}
body, h1, h2, h3, h4, h5, h6, hr, p, blockquote, dl, dt, dd, ul, ol, li, pre, fieldset, lengend, button, input, textarea, th, td {
	margin: 0;
	padding: 0;
}
/* 各种字体矫正 --------- */
body, button, input, select, textarea { font: 14px/1 Microsoft YaHei, Tahoma, Helvetica, Arial, "\5b8b\4f53", sans-serif; }
h1 { font-size: 18px; }
h2 { font-size: 16px; }
h3 { font-size: 14px; }
h4, h5, h6 { font-size: 100%; }
button, input, select, textarea {
	font-size: 100%;
	outline: none;
}
address, cite, dfn, em, var { font-style: normal; }
code, kbd, pre, samp, tt { font-family: "Courier New", Courier, monospace; }
small { font-size: 12px; }
/* 重置列表元素 --------- */
ul, ol { list-style: none; }
/* 重置文本格式元素 ----- */
a { color: #333; }
a, a:hover { text-decoration: none;  }
a:hover {color: #12833b;}
a:focus { outline: none; }
abbr[title], acronym[title] {
	border-bottom: 1px dotted;
	cursor: help;
}
q:before, q:after { content: ''; }
/* 重置表单元素 ------- */
legend { color: #000; }
fieldset, img { border: none; }
/* 重置表格元素 ------ */
table {
	border-collapse: collapse;
	border-spacing: 0;
	text-align: left;
}
table th { font-weight: normal; }
/* 重置 hr --------- */
hr {
	border: none;
	height: 1px;
}
/****** reset 基本样式重置 end   ******/
/****** 复用性样式设置 strat ******/
.clearfix:after {
	content: "\200B";
	display: block;
	height: 0;
	clear: both;
}
.clearfix { *zoom:1;
}
.clear{
	display:block; 
	clear:both; 
	font-size:0; 
	line-height:0; 
	height:0; 
	overflow:hidden; 
	content:".";
}
/****** 复用性样式设置 end   ******/
```

