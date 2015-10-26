---
layout: post
title: 低版本IE浏览器对cloneNode方法的实现差异
tags: IE cloneNode 差异
categories: 技术 Javascript
---

&#160; &#160; &#160; &#160; 之前在项目中使用了cloneNode方法对对象进行拷贝，结果在前期运行没有问题，上线之后功能时有异常。经过检查，发现被IE浏览器给坑了。
低版本IE对cloneNode方法的实现有别于其他浏览器。

---


#### 1. IE6/7中cloneNode方法无法复制radio的选中状态

代码：

{% highlight HTML %}
	<input type="radio" checked="true" value="1"/>
	<input type="checkbox" checked="true" value="1"/>
	<script>
		var input = document.getElementsByTagName('input')[0];
		var clone = input.cloneNode(true);
		alert(clone.checked);
	</script>
{% endhighlight %}

运行结果：

> IE6/7 : false
> 
> IE8/9/Firefox12/Chrome18/Safar5/Opera11 : true
	
   
   &#160;
   
#### 2. IE6/7/8 中cloneNode方法无法复制input\[type=text\]和textarea的defaultValue属性值	
	
代码：
{% highlight HTML %}

<input value="hello"/>
<script>
	var input = document.getElementsByTagName('input')[0];
	var clone = input.cloneNode(true);
	alert(clone.defaultValue);
</script>

{% endhighlight %}

运行结果：

>  IE6/7/8 : ""
>
>  IE9/Firefox12/Chrome18/Safar5/Opera11 : "hello"

&#160;

#### 3. IE6/7/8中cloneNode方法无法复制option的selected值

{% highlight HTML %}

<select>
	<option value="1">1</option>
	<option value="2" selected="selected">2</option>
	<option value="3">3</option>
</select>
<script>
	var option = document.getElementsByTagName('option')[1];
	var clone = option.cloneNode(true);
	alert(clone.selected);
</script>

{% endhighlight %}

运行结果：

> IE6/7/8 : false
> 
> IE9/Firefox12/Chrome18/Safar5/Opera11 : true


&#160;
	
#### 4. IE6/7/8中cloneNode方法无法复制script的text属性值

{% highlight HTML %}

<script>
	var a = 'test';
</script>
<script>
	var script = document.getElementsByTagName('script')[0];
	var clone = script.cloneNode(true);
	alert(clone.text)
</script>

{% endhighlight %}

运行结果：

> IE6/7/8 : ""
> 
> IE9/Firefox12/Chrome18/Safar5/Opera11 : "var a = 'test';"


--- 

原文链接：[各浏览器cloneNode方法的部分实现差异](http://www.cnblogs.com/snandy/archive/2012/05/06/2473936.html)

