---
author: xjh1994
comments: true
date: 2013-04-23 05:00:11+00:00
layout: post
slug: '%e3%80%90linux%e3%80%91%e4%bd%bf%e7%94%a8make%e5%91%bd%e4%bb%a4%e5%92%8cmakefile%e6%96%87%e4%bb%b6%e7%bc%96%e7%a8%8b'
title: 【LINUX】使用make命令和makefile文件编程
wordpress_id: 93
categories:
- Linux
tags:
- Linux
- make
- makefile
---

make工具可以在必要时重新编译所有受改动影响的源文件，极大地提高效率。




## make命令和makefile文件




make命令和makefile文件的结合提供了一个在项目管理领域十分强大的工具。它不仅常被用于控制源代码的编译，而且还用于手册也的编写以及将应用程序安装到目标目录。




### makefile的语法




makefile文件由一组依赖关系和规则构成。每个依赖关系由一个目标（即将要创建的文件）和一组该目标所依赖的源文件组成。而规则描述了如何通过这些依赖文件创建目标。一般说来，目标是一个单独的可执行文件。

make命令会读取makefile文件的内容，它首先确定目标文件或要创建的文件，然后比较该目标锁依赖的源文件的日期和时间以决定该采取哪条规则来构造目标。通常在创建最终目标文件之前，它需要先创建一些中间目标。make命令根据makefile文件来确定目标文件的创建顺序以及正确的规则调用顺序。




### make命令的选项和参数




最常用的三个选项如下所示：

-k或者--keep-going
执行命令遇到错误时不终止make的执行，make尽最大可能执行所有的命令，直到出现致命错误才终止

-f filename或者--file=FILE或者--makefile=FILE
使用指定文件作为makefile文件

-n或者--just-print或者--dry-run
只打印出要执行的命令



注意，如果未使用-f选项，那么婊子版本的make命令会首先在当前目录下查找名为makefile的文件。如果该文件不存在，会查找名为Makefile文件。但是如果是在Linux系统中，使用的可能是GNUMake，这个版本的make命令将在搜索makefile文件和Makefile文件之前首先查找名为GNUMakefile的文件。按照管理，许多linux程序员使用文件名Makefile。



为了指示make命令创建一个特定的目标，可以把该目标的名字作为make命令的一个参数。如果不这样做，make命令将试图创建列在makefile文件中的第一个目标。同菜的做法是在makefile文件中将第一个目标定义为all，然后再列出其他从属目标。这个约定明确告诉make命令，在未指定特定目标时，默认情况下应该创建哪个目标。



**依赖关系**

依赖关系定义了最终应用程序里的每个文件与源文件之间的关系。



比如，有如下源代码：










**[cpp][/cpp]** [view plain](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[copy](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[print](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[?](http://blog.csdn.net/xiajun07061225/article/details/8513682#)












	
  1. //main.c

	
  2. #include "a.h"

	
  3. 
	
  4. //2.c

	
  5. #include "a.h"

	
  6. #include "b.h"

	
  7. 
	
  8. //3.c

	
  9. #include "b.h"

	
  10. #include "c.h"





在这个例子中可以把依赖关系定义为最终应用程序依赖与文件main.o、2.o和3.o。同样，main.o依赖于main.c和a.h等等。。。





在makefile文件中，这些规则的写法为：先写目标的名称，然后紧跟一个冒号，接着是空格或制表符tab隔开的文件列表。如下：










**[cpp][/cpp]** [view plain](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[copy](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[print](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[?](http://blog.csdn.net/xiajun07061225/article/details/8513682#)












	
  1. myapp: main.o 2.o 3.o

	
  2. main.o: main.c a.h

	
  3. 2.o: 2.c a.h b.h

	
  4. 3.o: 3.c b.h c.h







**规则**

makefile文件的第二部分是规则。归则定义了目标的创建方式。

需要特别注意的是：在makefile文件中空格和制表符tab是有区别的。规则所在的行必须以tab开头，用空格是不行的。



针对前面的例子，这个Makefile文件可以这样写：










**[cpp][/cpp]** [view plain](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[copy](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[print](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[?](http://blog.csdn.net/xiajun07061225/article/details/8513682#)












	
  1. myapp: main.o 2.o 3.o

	
  2.     gcc -o myapp main.o 2.o 3.o

	
  3. main.o: main.c a.h

	
  4.     gcc -c main.c

	
  5. 2.o: 2.c a.h b.h

	
  6.     gcc -c 2.c

	
  7. 3.o: 3.c b.h c.h

	
  8.     gcc -c 3.c





运行结果：



![](http://img.my.csdn.net/uploads/201301/17/1358410255_4243.png)

![](http://img.my.csdn.net/uploads/201301/17/1358410358_7752.png)

源代码：

a.h和c.h为空。

b.h：










**[cpp][/cpp]** [view plain](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[copy](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[print](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[?](http://blog.csdn.net/xiajun07061225/article/details/8513682#)












	
  1. #include <unistd.h>

	
  2. #include <stdio.h>

	
  3. #include <stdlib.h>







2.c：










**[cpp][/cpp]** [view plain](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[copy](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[print](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[?](http://blog.csdn.net/xiajun07061225/article/details/8513682#)












	
  1. #include "a.h"

	
  2. #include "b.h"

	
  3. void function_two()

	
  4. {

	
  5.     printf("The function_two is invoked!n");

	
  6. }





3.c：












**[cpp][/cpp]** [view plain](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[copy](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[print](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[?](http://blog.csdn.net/xiajun07061225/article/details/8513682#)












	
  1. #include "b.h"

	
  2. #include "c.h"

	
  3. 
	
  4. void function_three()

	
  5. {

	
  6.     printf("The function_three is invoked!n");

	
  7. }





main.c：












**[cpp][/cpp]** [view plain](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[copy](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[print](http://blog.csdn.net/xiajun07061225/article/details/8513682#)[?](http://blog.csdn.net/xiajun07061225/article/details/8513682#)












	
  1. #include <stdlib.h>

	
  2. #include "a.h"

	
  3. 
	
  4. extern void function_two();

	
  5. extern void function_three();

	
  6. 
	
  7. int main()

	
  8. {

	
  9.     function_two();

	
  10.     function_three();

	
  11. 
	
  12.     exit(EXIT_SUCCESS);

	
  13. }



