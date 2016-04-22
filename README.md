Linux011
========

Linux 0.11 版本源码

可参考 http://oldlinux.org/index_cn.html
源码在 http://oldlinux.org/Linux.old/

- [http://oldlinux.org/Linux.old/images/](http://oldlinux.org/Linux.old/images/) 该目录包含已经制作好的内核映像文件bootimage和根文件系统映像文件 rootimage
- [http://www.oldlinux.org/Linux.old/kernel/](http://www.oldlinux.org/Linux.old/kernel/)该目录包含内核原代码程序，包括 Linux 0.11 内核源代码程序。
- [http://www.oldlinux.org/Linux.old/bochs/](http://www.oldlinux.org/Linux.old/bochs/)该目录中包含有已经设置好的运行在计算机仿真系统bochs下的linux系统。
- [http://www.oldlinux.org/Linux.old/Linux-0.11/](http://www.oldlinux.org/Linux.old/Linux-0.11/)该目录中含有可以在 Linux 0.11 系统中使用的其他一些工具和原来发布的一些安装说明文档。


主页在 http://jinghang.github.io/Linux011/

http://wiki.osdev.org/Main_Page

# 源码说明
- src/V0.11/ 目录放的是当年Linus写的源码，
- src/V0.11_gcc4/ 目录放的是可以在gcc4编译通过的内核源码，
- src/V0.11_rh9/ 目录放的是在RetHat9系统下编译通过的内核源码。

# 编译记录
- 2016.4.12
出现 strcpy 重定义 gcc5 和以前的 gcc 对 extern inline 理解不同，给 CFLAGS 加 -fgnu89-inline 表示使用旧版的 gcc ，详情[http://blog.csdn.net/force_eagle/article/details/11106571](http://blog.csdn.net/force_eagle/article/details/11106571)<br/>
__stack_chk_fail找不到引用问题 CFLAGS 加 -fno-stack-protector

# 编译 bochs
- 安装所需类库
	`sudo apt-get install xorg-dev`
- 配置
	`./configure --enable-debugger -- enable-disasm`

	`--enable-debugger`   加入调式功能，
	`--enable-disasm`     反汇编，
	`--enable-gdb-stub`    GDB通信

	`--enable-debugger` 和 `--enable-gdb-stub` 只能放一个 http://blog.chinaunix.net/uid-26258259-id-3792406.html

- 编译
	`make`

- 安装
	`sudo make install`

- 卸载
	`sudo make uninstall`


## gui调式
https://code.google.com/archive/p/peter-bochs/

https://github.com/mcheung63/GKD


# 寄存器说明
http://www.cnblogs.com/zhaoyl/archive/2012/05/15/2501972.html<br/>
http://blog.csdn.net/knxw0001/article/details/7249248

