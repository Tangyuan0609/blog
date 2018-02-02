---
title: 触发input手机输入键盘遮挡input(苹果手机)
tags: [移动端,兼容问题]
categories: [移动端]
---

### 问题：测试移动端页面的时候，偶然发现点击底部input输入框时，input是固定在底部，弹出的虚拟键盘偶尔会挡住input输入框。

#### 解决思路：点击input输入框的时候，让其input滚动到当前div的顶部。于是我想到了Element.scrollIntoView() 方法。

#### 方法：击输入框的时候给input绑定事件，使用 Element.scrollIntoView()方法使元素弹到祖元素可见区域的顶部。代码如下：

``` js
$("input").on("click", function() {
	var target = this;
	setTimeOut(function() {
		target.scrollIntoView(true);
		}, 100);
})
``` 
