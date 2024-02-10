---
title: Linux gcc的使用
date: 2023/10/16  16:40:00
categories:
- [Linux]
tags:
- Linux
---

一次前端JS的学习记录。

<!-- more -->
# GCC基础使用

- -c参数

  激活预处理，编译，把程序做成obj文件

  ```bash
  gcc -c hello.c
  ```

- -S参数

  只激活预处理和编译，把文件译成汇编代码

  ```bash
  gcc -S hello.c
  ```

- -o参数

  指定目标名称，默认gcc编译之后为a.out

  ```bash
  gcc -o hello hello.c
  ```

- -O0/O1/O2/O3

  开启O优化
  
- -IDIRECTORY	指定额外的头文件搜索路径DIRECTORY。

  ```bash
  gcc -I ./head/
  ```

  

- -LDIRECTORY	指定额外的函数库搜索路径DIRECTORY。

  ```bash
  gcc -L ./src/
  ```

  

- -lLIBRARY	连接时搜索指定的函数库LIBRARY。





# 课件上的命令

-E 执⾏到预编译，进⾏代码⽂本的替换操作。输出预编译结果到标准输出（⼀般是显示器）

 -S 执⾏到汇编，进⾏源代码到汇编代码的转换，输出汇编代码（.s⽂件）

 -c 执⾏到编译，输出⽬标⽂件（.o⽂件）

 -o 制定⽬标名称, 默认的时候, gcc 编译出来的⽂件是 a.out -shared 与 

-fPIC：创建动态库

 • -fPIC：（Position-Independent Code）它作⽤于编译阶段，告诉编译器要⽣成与位置⽆关的代码（.o⽂件）

 • -shared：将多个.o⽂件链接成⼀个.so动态库⽂件 

-I(⼤写的i)：向gcc中加⼊头⽂件搜索路径 

-L：向gcc中加⼊库路径

 -static：链接静态库 

-w：关闭警告

 -Wall：开启所有警告

 -g：产⽣带有调试信息的⽬标代码