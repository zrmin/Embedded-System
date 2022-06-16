<h1><center>Linux驱动</center></h1>

## 一、编写Linux驱动

1. 包含头文件

   ```C
   #include<linux/init.h>
   #include<linux/module.h>
   ```

2. 入口出口

   ```C
   module_init();
   molude_exit();
   ```

3. 声明

   ```C
   MODULE_LICENSE("GPL");
   ```

4. 功能实现

   ```C
   static int hello_init(void) {
       printk("hello world\n");
       return 0;
   }
   
   static void hello_exit(void) {
       printk("bye bye\n");
   }
   ```



完整程序如下：

```C
#include<linux/init.h>
#include<linux/module.h>

static int hello_init(void) {
    printk("hello world\n");
    return 0;
}

static void hello_exit(void) {
    printk("bye bye\n");
}

module_init(hello_init);
module_exit(hello_exit);

MODULE_LICENSE("GPL");
```



## 二、编译驱动代码

<p>方法一：把驱动编译成模块，然后使用命令把驱动加载到内核</p>

1. 编写makefile

   ```makefile
   obj-m +=helloworld.o
   
   KDIR:=/usr/src/内核源码位置
   
   PWD?=$(shell pwd) ;当前文件位置
   
   all:
   	make -C $(KDIR) M=$(PWD) modules
   ```

2. 编译驱动

   ```shell
   make ; make后出现的helloworld.ko文件就是驱动模块
   ```

3. 加载驱动模块

   ```shell
   sudo insmod helloworld.ko
   ```

4. 查看加载的模块

   ```shell
   lsmod
   ```

5. 卸载驱动模块

   ```shell
   sudo rmmod helloworld ;注意没有.ko后缀
   ```

   