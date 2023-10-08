---
title: Linux基础命令学习
date: 2023/10/08  8:30:00
categories:
- [Linux]
tags:
- 后端

---

linux基础命令的学习。

<!-- more -->

## linux基础命令

1. 创建一个指向文件或目录的软连接

   创建一个/tmp/dir1/的软连接link1

   ```shell
   sudo ln -s /tmp/dir/ link1
   ```

2. 创建一个指向文件或目录的物理连接

   创建一个指向/tmp/test的物理连接link2

   ```shell
   sudo ln /tmp/test link2
   ```

   物理链接指向原链接文件地址，它会在你选定的位置上生成一个和源文件大小相同的文件

3. 修改一个文件或者目录的时间戳

   设置/tmp/test文件的时间戳

   ```shell
   sudo touch -t 0712250000 /tmp/test
   ```

   使用`ll`命令来查看，此命令同时可以查看文件权限

4. 设置目录的所有人(u)、群组(g)以及其他人(o)以及读(r)、写(w)和执行(x)的权限

   修改/tmp/目录的权限

   ```shell
   sudo chmod ugo+rwx /tmp/test
   ```

5. 删除群组(g)与其他人(o)对目录的读写执行权限

   删除群组(g)与其他人(o)对当前目录/tmp的读写执行权

   ```shell
   sudo chmod go-rwx .
   ```

## linux 磁盘、内存与进程分析

1. ps命令查看进程信息

   ```shell
   ps -aux
   ```

2. 查看某一程序的进程信息

   现在假如我们想找到openbox这个进程的信息，可以通过grep来筛选，在命令行运行下面的命令

   ```shell
   ps -ef | grep openbox
   ```

3. 查看某进程的cup和内存占用情况

   ```shell
   top -p 105(pid)
   ```

4. 查询某进程的详细信息

   ```shell
   cat /proc/105(pid)/status
   ```

5. 查看系统内存的使用情况

   ```shell
   free -m
   ```

6. 查看磁盘空间使用情况

   ```shell
   df -Th
   ```

## linux 软件包安装，删除，配置和管理

1. 展示所有可安装的程序

   ```shell
   sudo dpkg -l
   ```

2. package 获取包的相关信息

   ```shell
   sudo apt-cache show tree
   ```

3. 查看软件安装路径

   ```shell\
   dpkg -L tree
   ```

4. 软件包的卸载

   ```shell
   sudo apt remove tree -y
   ```

   



