<h1> <center>嵌入式系统article（一）</center> </h1>

<h2><center>前言</center></h2>

这是我们开学的第一周，由于疫情原因，一半人在线上、一半人在线下。

现对本周的嵌入式系统学习做个简单回顾。

## 一、嵌入式系统简介

嵌入式系统，是一种specialized computer system，它是软件和硬件的综合体。主要由以下4个部分组成：

1. 硬件层
2. 驱动层（中间层）
3. 系统软件层
4. 应用软件层



## 二、C语言中的重点

嵌入式系统由于需要操作底层硬件，因此使用的语言为C语言。在C语言中，最重要的是指针和结构体。

### （一）指针

在之前学习C语言时，我们就经常可以听到一种说法：<i>指针是C语言的灵魂</i>。为什么呢？因为指针赋予了程序员直接操控内存的能力。



### （二）结构体

C语言的结构体不像C++等面向对象风格的程序设计语言那样，可以在结构体struct或类class中封装属性和函数两个部分。在C语言的struct中，无法直接写入函数。但是，我们可以在struct中包含函数指针。函数指针的用法我们已经非常熟悉了。这种做法，我们在操作系统的内核代码中司空见惯了。我说一下这种做法的我的理解：<font color = red>为了模拟面向对象的风格</font>。我们常说C语言是面向过程的语言，C++、Java是面向对象的语言。其实，面向过程与面向对象只是不同的编程思想、不同的编程风格。既然是风格，我们就可以模拟出来。使用C语言来模拟面向对象的风格，需要使用到函数指针，当然不只有函数指针，为了模拟类的继承还需要有类指针。不便深入。



## 三、数据存储与读取

数据存储在分配的内存中。内存分配在哪里呢？分配的空间的大小又是多少呢？这需要依靠数据类型来决定。不同类型的数据存储在不同的内存区域中、数据在存储的时候需要遵循自然对齐的规则等等。不便深入。

数据在读取的时候，需要根据其存储的内存首地址和内存大小取出01机器码，然后对齐进行指定的翻译。那么存储的首地址如何确定呢？这就涉及到大头优先和小头优先的硬件设计了。我们的个人计算机PC上，intel的CPU是小头优先的。





