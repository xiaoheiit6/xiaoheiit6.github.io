---
title: Kotlin学习
date: 2023/08/30  19:30:00
categories:
- [Kotlin]
tags:
- 后端
---

Kotlin的速成。

<!-- more -->

## 数据类型

- 数据类型的定义

  - 变量

    ```kotlin
    fun main(){
        //变量的定义
        //指定类型 其中的Int是一个对象
        var name:Int = 1
        //不指定类型，kt会进行自动推导
        var name = 1
        //如果是小数，则会被自动推导为double类型
        //double类型：
        var name = 1.2
        //float类型 需要在小数后边加f或者F
        var name = 1.2f
        //长整型 在数后边加L
        var name = 1L
    }
    ```

  - 常量

    ```kotlin
    fun main(){
        //常量的定义
        val a:Int = 1
    }
    ```

- 字符串的相关操作

  - get方法

    ```kotlin
    fun main(){
        var data = "hello"
        //输出 h
        println(data.get(0))
        //同时可以这样写
        println(data.[0])
    }
    ```
    
  - equals方法
  
    ```kotlin
    fun main(){
        var data_01 = "hello"
        var data_02 = "hello"
        var data_03 = "hello world"
        //输出为TRUE
        println(data_01.equals(data_02))
        //输出为FALSE
        printlin(data_01.equals(data_03))
     }
    ```
  
  - 拼接文本
  
    ```kotlin
    fun main(){
        var a = "world"
        var data = "hello ${a}"
        //输出结果： hello world
        println(data)
    }
    ```
  
  - 多行字符串
  
    ```kotlin
    fun main(){
        var data = """
        line1
        line2
        line3
        """.trimIndent()
    }
    ```
  
- 数组相关

  - 数组的创建

    ```kotlin
    fun main(){
        //第一种创建方式 使用函数arrayOf来进行创建
        //[1, 2, 3]
        val a = arrayOf(1, 2, 3)
        //第二种创建方式 使用工厂函数
        //[0, 2, 4]
        val b = Array(3, {i -> (i*2)})
    }
    ```

  - 数组的操作
  
    ```kotlin
    fun main(){
        //读取数组的内容 []对应调用成员函数的get()和set()方法
        println(a[0])
        println(a[1])
        //使用get() set() 一样可以实现
        println(a.get(0))
        a.set(0, 2)
        println(a.get(0)) //输出为2
    }
    ```
  
    注意：与Java不同的是，Kotlin中的数组是不型变的(invariant)
  
    除了Array类，还有其他比如IntArray，ShortArray等，表示各种的数组，省去了装箱的操作，效率更高，其用法与ArrayOf一样：
  
    ```kotlin
    val x: IntArray = intArrayOf(i, 2, 3)
    x[0] = x[1] + x[2]
    ```

- list

  - list的创建

    ```kotlin
    fun main(){
        //默认出创建空的list
        val list = listOf<Int>()
        //判断是否为空
        println(list.isEmpty())
    }
    ```

    注意这种创建的list是不可变的

    可变list的创建：

    ```kotlin
    fun main(){
        
    }
    ```

**写到这又去看数学建模去了。。**