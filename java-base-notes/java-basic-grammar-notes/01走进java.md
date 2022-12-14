# 计算机编程语言

## 计算机编程语言的发展

第一代:机器语言,二进制

第二代:汇编语言,一种助记符

第三代:高级语言.

 C、Pascal、Fortran面向过程的语言
 C++面向过程/面向对象
 Java跨平台的纯面向对象的语言
 .NET跨语言的平台
 Python、Scala…

## 计算机语言排行榜

网址:

https://www.tiobe.com/tiobe-index/



# java历史与背景

后台开发：Java、PHP、Python、Go、Node.js

## java语言的诞生

前身:1991年 Green项目，开发语言最初命名为Oak (橡树)

SUN(Stanford University Network，斯坦福大学网络公司 ) 1995年推出jdk1.0

java之父James Gosling

2009 oracle公司收购sun



## java语言的发展

 1991年 Green项目，开发语言最初命名为Oak (橡树)
 1994年，开发组意识到Oak 非常适合于互联网
 1996年，发布JDK 1.0，约8.3万个网页应用Java技术来制作
 1997年，发布JDK 1.1，JavaOne会议召开，创当时全球同类会议规模之最
 1998年，发布JDK 1.2，同年发布企业平台J2EE
 1999年，Java分成J2SE、J2EE和J2ME，JSP/Servlet技术诞生
 2004年，发布里程碑式版本：JDK 1.5，为突出此版本的重要性，更名为JDK 5.0
 2005年，J2SE -> JavaSE，J2EE -> JavaEE，J2ME -> JavaME
 2009年，Oracle公司收购SUN，交易价格74亿美元
 2011年，发布JDK 7.0
 2014年，发布JDK 8.0，是继JDK 5.0以来变化最大的版本
 2017年，发布JDK 9.0，最大限度实现模块化
 2018年3月，发布JDK 10.0，版本号也称为18.3
 2018年9月，发布JDK 11.0，版本号也称为18.9

 2018年9月，发布JDK 11.0，版本号也称为18.9

至今最新版是jdk17也是稳定版

java8,java11,java17是LTS长期支持版本

jdk10开始Oracle加快发布速度,大概每6个月发布一次



# java应用领域

企业级应用:大流量

桌面应用:各种管理软件

移动应用：安卓平台,

大数据平台：大数据开发的软件

科学计算的软件

嵌入式开发



java应用方向主要:

企业级应用,Android平台应用,大数据平台开发(各类框架有Hadoop，spark，storm，flink等)



# java语言特点

面向对象

跨平台性(核心)

多线程

分布式:java语言就是为分布式系统而设计的

......



# java三大平台

Java SE(Java Standard Edition)标准版:台式机和工作站桌面级应用,最牛的是浏览器+服务器

javaSE包含JRE,JDK和java核心类库JRE中包含JVM,JDK包含了JRE和一些开发工具,这些工具包括编译器,文档生成器和文件打包等工具

SE中还提供了基本类库和核心类库,包括字符串,集合,IO,网络和图形界面等.

学习java就是学习java语法和类库的用法



Java EE(Java Enterprise Edition)企业版:Web应用程序开发

EE是以SE为基础,并提供了一套服务,API接口和协议,能开发企业级分布式系统,WEB应用程序和业务组件等

其中包括JSP,Servlet,EJB,JNI和Java Mail



Java ME(Java Micro Edition)小型版:移动终端(早期塞班的应用程序开发,ME凉掉了)



# java虚拟机

java应用程序 --> java虚拟机 --> 操作系统 --> 硬件



# java跨平台原理

java跨平台原理教程黑马:

https://www.bilibili.com/video/BV17F411T7Ao?p=15&vd_source=e3c1a57c5f8561699e8f4460cc5ae27d

C编译型,整体翻译

Python解释型,用一行翻译一行

java混合型

java应用程序能够跨平台运行,主要通过虚拟机实现

不同操作系统有对应的jvm,在jvm中运行java代码

java程序 --> java虚拟机 --> 操作系统 --> 计算机硬件



# java程序运行机制

java源文件 --> 编译器 --> .class文件 --> 解释器 --> 计算机 



# jdk和jre关系

JRE和JDK关系黑马:

https://www.bilibili.com/video/BV17F411T7Ao?p=16&spm_id_from=pageDriver&vd_source=e3c1a57c5f8561699e8f4460cc5ae27d

javaSE中包含:JRE,JDK和java核心类库

JRE是对JDK的抽离,当编写好代码编译成class文件,放到别人电脑中运行,很多工具用不到,并不需要完整的jdk进行支持,为了省空间,直接从jdk抽离出JRE运行时环境支持运行class文件即可

不考虑开发java应用程序,那么只需要安装JRE就可以了,JRE中有运行所需的JVM



# java学习路线

黑马程序员java学习路线:

http://yun.itheima.com/subject/javamap/index.html?ku-a2$zy

尚硅谷学习路线:

https://www.bilibili.com/video/BV1Kb411W75N/?spm_id_from=333.337.search-card.all.click(评论区)

how2j学习路线:

https://how2j.cn/frontroute

