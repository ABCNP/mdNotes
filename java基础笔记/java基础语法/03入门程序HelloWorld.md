# 编写程序

老版本需要先配置环境变量,新版本直接使用

使用Notepad++/记事本编写以下代码保存

```java
public class HelloWorld{
	public static void main(String[] args){
		System.out.println("Hello,World!");
	}
}
```

# 编译文件

在文件所在处使用dos命令编译文件

> javac HelloWorld.java



# 运行文件

使用命令运行文件

> java HelloWorld

java11开始支持java直接运行源代码文件

命令

> java HelloWord.java

会输出 :Hello,World!这段话

底层先生成一个临时的class文件,文件夹不会显示,



如果出现乱码:

> javac -encoding UTF-8 HelloWord.java



流程三步:

编写程序,编译文件,运行程序



# java源文件

扩展名.java后缀的源文件



# 编译源文件

将源文件编译成.class后缀的字节码文件,但是字节码文件是给虚拟机看的,人看不懂

想要看可以反编译class文件,就能看到程序指令



# 主方法

main方法程序入口



# 控制台输出

将输出信息打印在控制台显示