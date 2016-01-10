Beyond Compare for mac 无限试用方法
=
* 原理：

	只要在在启动的时候删除registry.dat (Library/Application Support/Beyond Compare/registry.dat)注册信息就好了.

* 操作：
	
	进入 beyond compare 应用程序的 MacOS 目录下(/Applications/Beyond Compare.app/Contents/MacOS)，BCompare 是应用程序启动的程序. 将主启动程序 BCompare 重命名为 BCompare.real

	在同级目录下新建一个脚本文件, 命名为 BCompare . 这样 BCompare 在启动的时候就会执行该脚本文件, 注意记得 chmod a+x BCompare。在这个脚本里面写如下代码:

		#!/bin/bash
		rm "/Users/$(whoami)/Library/Application Support/Beyond Compare/registry.dat"
		"`dirname "$0"`"/BCompare.real &

		第一行是注明解释器，第二行是删除注册信息，第三行是启动真正的主程序。
