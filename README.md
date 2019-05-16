# How-to-install-a-Hackintosh

作者：Genius-lbesT QQ2489050703

加入QQ群：724096369 黑苹果Genius

转载请注明出处

前言：

本教程主旨在于指导正确的安装一个黑苹果系统，其中包括了一下的内容：

如何制作UEFI引导安装的MAC OS安装U盘？

如何替换ESP分区中的UEFI引导文件？

如何建立由UEFI引导的MAC/WIN？

如何修复mbr引导的win，使它可以无损的转换成uefi引导的系统？

正文：

如何正确的安装一个黑苹果系统

一、首先你需要下载几样东西，其中包括：

（1）镜像
镜像下载地址：

Mojave10.14.5:https://blog.daliansky.net/macOS-Mojave-10.14.5-18F132-official-version-with-Clover-4928-original-image.html

Mojave10.14.4:https://blog.daliansky.net/macOS-Mojave-10.14.4-18E226-official-version-with-Clover-4903-original-image.html

10.13.6(17G65):https://blog.daliansky.net/macOS-High-Sierra-10.13.6-17G65-Release-Version-with-Clover-4596-original-mirror.html

（2）Etcher

下载地址：http://etcher.io/

（3）DG分区工具DiskGenius（下文称为DG)：

链接:https://pan.baidu.com/s/126xM0Hd-VV3JAmBCLRfJ0w  密码:on1y

（4）8G或大于8G的U盘

二、制作安装系统U盘

（1）win下制作

-----安装Etcher

-----打开Etcher-选择镜像-选择U盘-点击Flash，等待完成

（2）mac下制作

-----插入u盘

-----打开 “应用程序 → 实用工具 → 磁盘工具”，将U盘「抹掉」(格式化) 成「Mac OS X 扩展（日志式）」格式、GUID 分区图，并将 U 盘命名为「USB」(下图序号3处)。注意：这个盘符名称必须与后面的命令里的名称一致，需要认真看清楚，很多新手容易出错在这里)

-----打开双击镜像xx.dmg，将镜像中的xx.app文件拖入application（应用程序）文件夹

-----打开 “应用程序→实用工具→终端”，将下面的一段命令复制并粘贴进去，运行：

--Mojave:

sudo /Applications/Install\ macOS\ Mojave.app/Contents/Resources/createinstallmedia --volume /Volumes/USB /Applications/Install\ macOS\ Mojave.app --nointeraction

--High Sierra

sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/USB --applicationpath /Applications/Install\ macOS\ High\ Sierra.app --nointeraction

-----挂载EFI

打开终端，输入命令：sudo diskutil mount disk0s1或者sudo diskutil mount EFI

-----将镜像中的EFI或适合你机器使用的EFI，复制到U盘的EFI分区

三、部署黑苹果的UEFI启动环境

UEFI启动需要你的磁盘为guid格式，对于mbr的磁盘，将磁盘转换为guid格式

实现此操作的几个方法：

1.win系统下对非win系统所在的磁盘直接使用DG对磁盘禁行转化

2.win所在的磁盘进行转化时，请在PE中启动DG，对磁盘进行转化，并调整C盘大小

实现此
