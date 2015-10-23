---
layout: post
title: Spring framework 单独jar包下载地址
tags: spring jar 下载
categories: 技术 资源
---

# 下载独立jar包

Spring framework 的相关jar包现在已经无法从官方直接下载了，官方只给出了[Maven和Gradle][spring_pom]两种依赖方式。
不过你可以在spring的官方repo中下载独立的jar包：
	
> [http://repo.spring.io/release/org/springframework/spring/][spring_jar]


# 使用Maven配置

## ```pom.xml```配置

{% highlight XML %}
<!-- Spring 4.2.0，其他版本只需要更改版本号 -->
<dependency>
	<groupId>org.springframework</groupId>
	<artifactId>spring-aop</artifactId>
	<version>4.2.0.RELEASE</version>
	<scope>compile</scope>
</dependency>
<dependency>
	<groupId>org.springframework</groupId>
	<artifactId>spring-aspects</artifactId>
	<version>4.2.0.RELEASE</version>
	<scope>compile</scope>
</dependency>
<dependency>
	<groupId>org.springframework</groupId>
	<artifactId>spring-beans</artifactId>
	<version>4.2.0.RELEASE</version>
	<scope>compile</scope>
</dependency>
<dependency>
	<groupId>org.springframework</groupId>
	<artifactId>spring-context</artifactId>
	<version>4.2.0.RELEASE</version>
	<scope>compile</scope>
</dependency>
<dependency>
	<groupId>org.springframework</groupId>
	<artifactId>spring-context-support</artifactId>
	<version>4.2.0.RELEASE</version>
	<scope>compile</scope>
</dependency>
<dependency>
	<groupId>org.springframework</groupId>
	<artifactId>spring-core</artifactId>
	<version>4.2.0.RELEASE</version>
	<scope>compile</scope>
	<exclusions>
		<exclusion>
			<groupId>commons-logging</groupId>
			<artifactId>commons-logging</artifactId>
		</exclusion>
	</exclusions>
</dependency>
<dependency>
	<groupId>org.springframework</groupId>
	<artifactId>spring-expression</artifactId>
	<version>4.2.0.RELEASE</version>
	<scope>compile</scope>
</dependency>
<dependency>
	<groupId>org.springframework</groupId>
	<artifactId>spring-instrument</artifactId>
	<version>4.2.0.RELEASE</version>
	<scope>compile</scope>
</dependency>
<dependency>
	<groupId>org.springframework</groupId>
	<artifactId>spring-jdbc</artifactId>
	<version>4.2.0.RELEASE</version>
	<scope>compile</scope>
</dependency>
<dependency>
	<groupId>org.springframework</groupId>
	<artifactId>spring-orm</artifactId>
	<version>4.2.0.RELEASE</version>
	<scope>compile</scope>
</dependency>
<dependency>
	<groupId>org.springframework</groupId>
	<artifactId>spring-tx</artifactId>
	<version>4.2.0.RELEASE</version>
	<scope>compile</scope>
</dependency>
<dependency>
	<groupId>org.springframework</groupId>
	<artifactId>spring-web</artifactId>
	<version>4.2.0.RELEASE</version>
	<scope>compile</scope>
</dependency>
<dependency>
	<groupId>org.springframework</groupId>
	<artifactId>spring-webmvc</artifactId>
	<version>4.2.0.RELEASE</version>
	<scope>compile</scope>
</dependency>
{% endhighlight %}



---

[spring_pom]: http://projects.spring.io/spring-framework/#quick-start
[spring_jar]: http://repo.spring.io/release/org/springframework/spring/