学习编程的基础四大件
数据结构和算法 学完之后要刷 leetcode（剑指offer）
计算机网络 tcp/ip 协议栈（tcp/ip详解）
操作系统 进程和线程 并发 和锁 内存分布调度等等 （深入理解操作系统）
设计模式 单例 工厂 代理 策略模式 模版方法（大话设计模式）

实践
Linux操作系统掌握 shell编程 脚本等等
编译/调试工具 Linux平台上 gcc 以及makefile（跟我一起写makefile）要会写 gdb调试工具

Linux系统编程  ！
多线程编程 网络编程（unix环境高级编程）（Linux高性能服务器编程）（posix多线程程序设计）

回想一下自己十多年花大精力学习过的技术，很多都已经随着时代的发展烟消云散了，剩下的都是长久不变的东西，主要包括：
C语言
Linux
OOD和抽象
网络和Web编程基础
分布式的基础知识
计算机基础知识

推荐书籍: 
C： C Primer Plus,  C和指针，C专家编程
基础四大件：
数据结构和算法：计算机程序设计艺术，大话数据结构，剑指offer，刷题。
计算机网络：TCP/IP详解
操作系统：深入理解操作系统
设计模式：大话设计模式

应用与编程实践：
    Linux：鸟哥的Linux私房菜 或 Linux就该这么学
    编译和调试工具材料：英语好的看GNU官方关于GCC和GDB的官方文档。中文版《debugging with gdb》,跟我一起写makefile
    Linux的环境编程：Unix环境高级编程 ，Linux高性能服务器编程，POSIX多线程程序设计


win: ipconfig
Linux: ifconfig (interface)
网卡 eth0 eth1

Bash是Bourne shell的后继兼容版本与开放源代码版本，它的名称来自Bourne shell（sh）的一个双关语（Bourne again / born again）：Bourne-Again SHell。

    Stephen Bourne wrote the shell for 7th edition Unix, released in 1979. This was called the Bourne shell, and was the standard shell on Unix for many years.
    When the GNU project decided to create an enhanced version of the shell, they chose to call it the “Bourne-again” shell, as a pun on “born again” while acknowledging the shell's roots.
Source: https://www.quora.com/Why-is-Bash-called-the-Bourne-again-shell

## 命令

sudo apt-get update  以后就可以上网了，为什么？
因为这个命令，会访问源列表里的每个网址，并读取软件列表，然后保存在本地电脑。我们在新立得软件包管理器里看到的软件列表，都是通过update命令更新的。
update后，可能需要upgrade一下。

sudo apt-get upgrade
这个命令，会把本地已安装的软件，与刚下载的软件列表里对应软件进行对比，如果发现已安装的软件版本太低，就会提示你更新。如果你的软件都是最新版本，会提示：

安装vmware-tools工具
但我的Ubuntu_16.04 LTS版本却仍不可虚拟机与原win10之间复制粘贴
执行下述三行命令：
    sudo apt-get autoremove open-vm-tools
    sudo apt-get install open-vm-tools
    sudo apt-get install open-vm-tools-desktop
然后重启完美解决问题。

ubuntu安装sshd
命令模式
i o a插入模式和shell一样esc返回，R取代
w保存
wq 保存并退出
q! 强制退出
p 粘贴

2.2 基础命令的操作, date, cal, bc
输入xx后再[Tab]两次为以xx为开头的命令, [ctrl]-c停止运行, [ctrl]-d编辑时exit，bc计算器

pwd
ls 
 -- help
touch创建文件
rm删除文件
rm -f 删除文件夹下文件
mkdir 创建文件夹
rmdir 删除文件夹
mv 重命名当前目录的该文件或将该文件移动道其他目录
cp 复制 -r 可以复制非空目录
echo 加入文本
>重定向
>
>>追加重定向

head -num 默认显示10行
tail -num默认显示尾部10行
more 按页
chmod 改权限(+或-或 r w x 8进制码表示)

正常模式 x剪切 d删除  y复制 p粘贴

gedit 图形界面文档编辑

    reboot, halt, poweroff关机重启等
    run level 0：关机
    run level 3：纯文本模式
    run level 5：含有图形接口模式
    run level 6：重新启动
    init 0
    
## Linux基本目录结构

![img](https://pic4.zhimg.com/80/v2-1f6cdbc3e0765ae8484624eaa2a08ab9_720w.jpg)


Linux 文件系统是一个**目录树的结构**，文件系统结构从一个根目录开始，根目录下可以有任意多个文件和子目录，子目录中又可以有任意多个文件和子目录

- **bin 存放二进制可执行文件(ls,cat,mkdir等)**
- boot 存放用于系统引导时使用的各种文件
- dev 用于存放设备文件
- **etc 存放系统配置文件**
- home 存放所有用户文件的根目录
- lib 存放跟文件系统中的程序运行所需要的共享库及内核模块
- mnt 系统管理员安装临时文件系统的安装点
- **opt 额外安装的可选应用程序包所放置的位置**
- proc 虚拟文件系统，存放当前内存的映射
- **root 超级用户目录**
- sbin 存放二进制可执行文件，只有root才能访问
- tmp 用于存放各种临时文件
- usr 用于存放系统应用程序，比较重要的目录/usr/local 本地管理员软件安装目录
- var 用于存放运行时需要改变数据的文件