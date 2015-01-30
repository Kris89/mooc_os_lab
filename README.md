# 注意
本处代码停止更新，已经合并到　https://github.com/chyyuu/ucore_lab
以后的更新将放在 https://github.com/chyyuu/ucore_lab

# 介绍(2014)

ucore OS是用于清华大学计算机系本科操作系统课程的OS教学试验内容。
ucore OS起源于MIT CSAIL PDOS课题组开发的xv6&jos、哈佛大学开发的
OS161教学操作系统、以及Linux-2.4内核。

ucore OS中包含的xv6&jos代码版权属于Frans Kaashoek, Robert Morris,
and Russ Cox，使用MIT License。ucore OS中包含的OS/161代码版权属于
David A. Holland。其他代码版权属于陈渝、王乃铮、向勇，并采用GPL License.
ucore OS相关的文档版权属于陈渝、向勇，并采用 Creative Commons 
Attribution/Share-Alike (CC-BY-SA) License. 

# 开发维护人员 

- [陈渝](http://soft.cs.tsinghua.edu.cn/~chen)  yuchen AT tsinghua.edu.cn
- 茅俊杰 eternal.n08 AT gmail.com

助教
============
何嘉权
徐永健
王  欢
陈一璋
...

# 实验内容

1. lab0 : 完成实验环境的搭建，熟悉基本的Linux命令和工具
1. lab1 ：启动操作系统
1. lab2 ：物理内存管理
1. lab3 ：虚拟内存管理
1. lab4 ：内核线程
1. lab5 ：用户进程
1. lab6 ：处理器调度
1. lab7 : 同步互斥
1. lab8 : 文件系统


# 实验环境
ucore OS实验主要在Linux环境下开发。如果你使用的是非Linux环境，则建议参考下面两种方法。

## Windows下基于MingW进行实验
- windows下如何配置ucore实验环境：这种方式不用安装Linux，感谢“下来障”同学提供的[配置教程](http://pan.baidu.com/s/1i3JxZZR)

## Windows下基于VirtualBox or VMWare进行实验

### 1. 安装VirtualBox or VMWare软件

VirtualBox虚拟机软件

  https://www.virtualbox.org/

[NOTICE] 也可以安装vmware虚拟机软件

### 2.使用已经预先安装好相关实验环境所需软件的虚拟硬盘

并下载已经安装好ubuntu 14.04  x86-64的虚拟硬盘文件压缩包。
[VirtualBox和虚拟硬盘文件压缩包](http://pan.baidu.com/s/1pJ4XTGZ)

--------------
[NOTICE] 可下载直接使用[同时用于vmware和virtualbox的OVA格式的虚拟硬盘文件mooc-os.ova]( http://pan.baidu.com/s/1gdePM6J)




压缩包可以用[haozip for windows软件](http://www.haozip.com)解压。解压压缩包后，可得到如下内容（大约4GB多）。 
```
\mooc-os\mooc-os.vbox
\mooc-os\mooc-os.vbox-prev
\mooc-os\mooc-os.vdi
```

如果此时你已经安装好了VirtualBox，在Windows资源管理器中双击文件“mooc-os.vbox”，
就可以在VirtualBox模拟的x86-64计算机中运行ubuntu 14.04  x86-64，并可以开始学习
ucore OS实验了。
```
用户名是 moocos
口令是 <空格键>
```

## 手动在VirtualBox虚拟机中安装ubuntu 14.04 和实验环境相关软件
（这里假定安装的要是ubuntu14.04 x86-64的系统）
-------------------------------------
1. 在VirtualBox上安装ubuntu 
下载ubuntu 14.04 img镜像，并在VirtualBox中安装系统。

建议a: 设置虚拟硬盘的大小为8GB以上，虚拟内存在512MB以上。
建议b: 如果你的机器安装的是32位的windows，则下载32位的ubuntu 14.04 img镜像。

2. 在ubuntu系统中安装实验环境相关软件
在shell（比如gnome-terminal）下可执行如下命令来安装相关软件 (“$”是shell的提示符，不用输入)
```
  $ sudo apt-get update
  $ sudo apt-get upgrade
  $ sudo apt-get install build-essential git qemu-system-x86 vim-gnome gdb make diffutils exuberant-ctags tmux openssh-server cscope meld
```
[NOTICE] 最小需要的安装包： build-essential git qemu-system-x86 gdb make diffutils 

# 练习步骤

进入VirtualBox中运行的ubuntu，点击左侧的gnome-terminal软件图标，可启动gnome-terminal
软件。在此软件中，执行如下命令：
1. 目前环境中已经有ucore lab源码，可进一步取得最新ucore lab源码
```
  $cd  moocos/ucore_lab  #到ucore lab所在目录
  $git pull   #取得最新的ucore lab源代码
  $cd
```
2. 学习源码
```
  $cd labX  #X为 1--8  
```
3. 阅读，修改源码，可以用understand软件或vim软件
```
  $understand
```
4. 修改完毕后，编译实验代码
```
  $make
```  
5. 如果编译无误，则可以运行测试一下
```
  $make qemu
```
6. 可以运行如下命令，看看自己的得分
  $make grade

# 相关资料


## 希望了解OS基本概念和原理的同学

 . [OS课程资料]( http://pan.baidu.com/s/1bncWxyv)    
 . [OS MOOC公开课(原理部分)](http://www.topu.com/mooc/4100)  

## 希望了解OS设计与实现细节的同学

 . [OS实验资料](http://pan.baidu.com/s/1i3vbdXV)     
 . [OS实验代码](https://github.com/chyyuu/mooc_os_lab)     
 . [OS MOOC公开课(实验部分)](http://www.topu.com/mooc/4100)  

## 希望自己动手实践OS的同学

 . ["操作系统简单实现与基本原理 — 基于ucore" (持续更新,变动较大) ](http://chyyuu.gitbooks.io/ucorebook/)
 . ["操作系统简单实现与基本原理 — 基于ucore" 配套代码](https://github.com/chyyuu/ucorebook_code)
 . [ucore plus 跨硬件平台的ucore OS](https://github.com/chyyuu/ucore_plus)


# UCORERS (代码贡献者)

茅俊杰、陈宇恒、刘聪、杨扬、渠准、任胜伟、朱文雷、
曹正、沈彤、陈旭、蓝昶、方宇剑、韩文涛、张凯成、
S郭晓林、薛天凡、胡刚、刘超、粟裕、袁昕颢...


# NOTICE

如果你发现了问题，有好的建议或意见,请给 yuchen AT tsinghua.edu.cn 发电邮；
如果你完成这8个实验，且对进一步探索、研究、研发操作系统感兴趣，请给 yuchen AT tsinghua.edu.cn 发电邮，欢迎加入我们的OS兴趣小组，共同进步！
