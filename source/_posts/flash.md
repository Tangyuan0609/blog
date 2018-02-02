---
title: flash遮挡弹出层
tags: [flash,兼容问题]
categories: [flash]
---

### wmode属性：

"Window " 在 Web 页上用影片自己的矩形窗口来播放应用程序，并且始终位于最顶层（默认属性）。
"Opaque " 显示页面上位于它后面的内容。
"Transparent "使 HTML 页的背景可以透过应用程序的所有透明部分显示出来，并且可能会降低动画性能。

#### 区别

1.Window速度快、有效率，但无法使用z-index，也没有办法混用于DHTML图层当中，这就是为什么常有人在抱怨自己的下拉菜单跑到Flash后面。

2.Opaque除了可以让你正确控制z-index的样式，也可以透过Javascript來控制它的大小或是移动swf的位置！不过要注意，Opaque的背景可是没有办法透明的，也就是说，任何內容都会被放在swf下面。

3.至于Transparent，想当然，就是把flash的背景变成透明。让swf档案可以融入网页当中而不会出现讨厌的白底，不过，transparent在IE里面是真的透明，也就是说，下面的网页內容是可以被选取起來的，但是在FF里面，就很讨厌了，因为虽然看起來透明，但是滑鼠卻无法点选。另外，要稍微注意的是，使用这个值，会让你的flash影片变得比较慢，从而影响性能！

### 解决方案

一、设置flash置底，加个代码：<paramname="wmode" value="opaque" />但是只加这个代码，IE可行，在FF下，失效。要想在FF下起作用，还要用在object　里加个　wmode="opaque" ，实例代码如下：

![](/images/flash1.png)

![](/images/flash2.png)
二、设置flash为透明：但是如果你在DW中插入动画，再加<param name="wmode" value="transparent">是不生效的。要把整个的flash插件代码换成如下：

``` js
<object type="application/x-shockwave-flash"data="http://www.w3net.cn/images/banner.swf" width="560″height="210″>
<param name="movie"value="http://www.w3net.cn/images/banner.swf" />
<param name="wmode" value="transparent" />
</object>
``` 

### Ckplayer解决方法：

Ckplayer.js参数设置地方加入，  wmode:‘Opaque‘,一共有两个地方，如果找不到，可以搜索allowScriptAccess: ‘always‘,在他下面加入即可。然后要修改弹出层的z-index，支持IE8

#### 注:[原本](http://www.bubuko.com/infodetail-1155925.html)http://www.bubuko.com/infodetail-1155925.html