---
layout: post
title: 使用Eclipse将工程打包成一个可以执行的Jar文件
tags: Eclipse 打包 Jar
categories: 技术 Java
excerpt: 使用Eclipse自带的导出功能将工程打包成一个可以执行的Jar文件
---

# Java实例程序

新建一个Jave Project，写一个Java类，该类必须包含```public static void main(String[] args) throws Exception```方法。

{% highlight Java %}
import org.apache.log4j.Logger;

public class JsoupTest {

	private static Logger logger = Logger.getLogger(JsoupTest.class);

	/**
	 * main方法作为入口
	 */
	public static void main(String[] args) throws Exception {
		System.out.println("hello " + args[0]);
	}

}
{% endhighlight %}

# 导出成可执行的Jar文件

## 使用Eclipse自带的导出功能
	

1. 右键需要导出的工程，选择```导出```
	
	![runable-jar-step1]({{ "/static/img/runable-jar-step1.png" |prepend: site.baseurl  }})
	
2. 在弹出的窗口中找到并选择```Runnable JAR file``` (在java分类下)，下一步
	
	![runable-jar-step2]({{ "/static/img/runable-jar-step2.png" |prepend: site.baseurl  }})
	
3. 在Launch configuration中找到含有main方法的入口类
	
	![runable-jar-step3]({{ "/static/img/runable-jar-step3.png" |prepend: site.baseurl  }})
	
4. 在Export destination选择导出的路径
		
	![runable-jar-step4]({{ "/static/img/runable-jar-step4.png" |prepend: site.baseurl  }})
	
5. 如果有用到外部jar包，可以在Library handing中选择jar包的处理方式
	
	![runable-jar-step5]({{ "/static/img/runable-jar-step5.png" |prepend: site.baseurl  }})
	
	三种方式略有不同，最后生成的jar包的样子分别是
	
	![runable-jar-step6]({{ "/static/img/runable-jar-step6.png" |prepend: site.baseurl  }})
	
6. 使用CMD运行程序。

	> 这一步也不是必须的，如果你的打包后的图标变成了Java图标 ![java_ico]({{ "/static/img/java_ico.png" |prepend: site.baseurl  }}) ，则可以直接双击运行。
	> 
	> 你也可以右键生成的jar包，选择使用Java来打开，区别就是这种方式不会显示控制台。
	
	
	在生成的jar包同级目录新建一个start.txt，打开并编辑：
	
		java -jar JsoupTest3.jar "world"
		pause
		
	保存。并重名成start.cmd：
	
	![runable-jar-step7]({{ "/static/img/runable-jar-step7.png" |prepend: site.baseurl  }})
	
7. 双击start.cmd，即可运行：

	![runable-jar-step8]({{ "/static/img/runable-jar-step8.png" |prepend: site.baseurl  }})
	
8. 如何向main方法中传入参数

		java -jar JsoupTest3.jar "world"
	
	这里的 ```world``` 就是传入的参数，在 main 方法中用 ```args[0]``` 就可以接受。
	
	如果是多个参数，使用 args[参数次序-1]就可以获得
	
	&#160;
	
## 使用 FatJar 插件打包

> 相比Eclipse自带的导出功能，FatJar 功能更为强大。 也可以在旧版本的eclipse上使用。
	
旧版本eclipse如何将工程打包成可执行的jar包，可以使用 fatjar 插件，具体移步 ***[这里](http://my.oschina.net/cloudcoder/blog/285047)***

&#160;

# 导出并生成 exe 程序

> Java可以将二进制程序打包成可执行jar文件，双击这个jar和双击exe效果是一样一样的，但感觉还是不同。打包成exe也需要这个可执行jar文件

具体请参考这里: [http://www.cnblogs.com/icewee/articles/2073203.html](http://www.cnblogs.com/icewee/articles/2073203.html)

&#160;


