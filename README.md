# How-to-install-a-Hackintosh

作者：**Genius-lbesT** QQ2489050703

加入QQ群：724096369 **黑苹果Genius**

转载请注明出处

前言：

#### 本教程主旨在于指导正确的安装一个黑苹果系统，其中包括了一下的内容：

如何制作UEFI引导的MAC OS安装U盘？

如何替换ESP分区中的UEFI引导文件？

如何建立由UEFI引导的MAC的分区？

如何修复mbr引导的win，使它可以无损的转换成uefi引导的系统？



## 正文：

如何正确的安装一个黑苹果系统

### 一、首先你需要下载几样东西，其中包括：

#### （1）镜像

镜像下载地址：

Mojave10.14.5:https://blog.daliansky.net/macOS-Mojave-10.14.5-18F132-official-version-with-Clover-4928-original-image.html

Mojave10.14.4:https://blog.daliansky.net/macOS-Mojave-10.14.4-18E226-official-version-with-Clover-4903-original-image.html

10.13.6(17G65):https://blog.daliansky.net/macOS-High-Sierra-10.13.6-17G65-Release-Version-with-Clover-4596-original-mirror.html

#### （2）Etcher

下载地址：http://etcher.io/

#### （3）DG分区工具DiskGenius（下文称为DG)：

链接:https://pan.baidu.com/s/126xM0Hd-VV3JAmBCLRfJ0w  密码:on1y

#### （4）「Clover Configurator」：

链接:https://pan.baidu.com/s/1BQmm0ujuQCwsqHDwJOjXug  密码:1psl

#### （5）8G或大于8G的U盘

![](https://github.com/Lubibest/How-to-install-a-Hackintosh/blob/master/1-download.jpg)

### 二、制作安装系统U盘

#### （1）win下制作

-----安装Etcher

-----打开Etcher-选择镜像-选择U盘-点击Flash，等待完成

![](https://github.com/Lubibest/How-to-install-a-Hackintosh/blob/master/2-FLASH.jpg)

#### （2）mac下制作

-----插入u盘

-----打开 “**应用程序 → 实用工具 → 磁盘工具**”，将U盘「**抹掉**」(格式化) 成「**Mac OS X 扩展（日志式）**」格式、**GUID 分区图**，并将 U 盘命名为「**USB**」。注意：这个盘符名称必须与后面的命令里的名称一致，需要认真看清楚，很多新手容易出错在这里)

![](https://github.com/Lubibest/How-to-install-a-Hackintosh/blob/master/3-USB.jpg)

-----打开双击镜像xx.dmg，将**镜像中的xx.app文件拖入application（应用程序）文件夹**

-----打开 “**应用程序→实用工具→终端**”，将下面的一段命令复制并粘贴进去，运行：

--**Mojave**:

sudo /Applications/Install\ macOS\ Mojave.app/Contents/Resources/createinstallmedia --volume /Volumes/USB /Applications/Install\ macOS\ Mojave.app --nointeraction

--**High Sierra**

sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/USB --applicationpath /Applications/Install\ macOS\ High\ Sierra.app --nointeraction

![](https://github.com/Lubibest/How-to-install-a-Hackintosh/blob/master/4-MAC-FLASH.jpg)

-----挂载EFI

打开终端，输入命令：**sudo diskutil mount disk0s1**或者**sudo diskutil mount EFI**

-----将镜像中的EFI或适合你机器使用的EFI，复制到U盘的EFI分区

![](https://github.com/Lubibest/How-to-install-a-Hackintosh/blob/master/5-EFI.jpg)

### 三、部署黑苹果的UEFI启动环境

#### （1）「UEFI启动模式」需要你的磁盘为「Guid格式」，对于「mbr格式」的磁盘，需要将「MAC目标安装磁盘」转换为「Guid格式」

实现此操作的几个方法：

1.win系统下对非win系统所在的磁盘直接使用DG对磁盘进行转化

2.win所在的磁盘进行转化时，请认真使用搜索工具进行转换操作，并修复WIN的引导

请备份好数据再进行操作，**数据无价**

如需无损转换，请添加我的QQ2489050703寻求技术支持

#### (2)建立ESP引导分区

——使用DG分区工具，对空闲的磁盘空间右键，「**新建ESP分区**」，分区大小为「**300M**」，取消勾选「**MSR分区**」，完成，「**保存分区表**」

-----由于DG分区工具的版本区别，如果无显示「**新建ESP分区的**」

解决方法：

对空闲的磁盘空间右键，「**新建分区**」，并选择格式为「**EFI**」，分区大小为「**300M**」，确认后，「**保存分区表**」

此时的ESP分区格式为「**FAT16**」，我们需要对该分区格式化为「**FAT32**」

#### （3）建立MAC OS系统安装分区

-----使用DG对磁盘空闲部分右键，新建分区，选择「**MAC日志式HFS+**」

PS：部分DG版本会先提示新建ESP分区，点取消，就会出现新建分区的界面

-----<保存分区表>

### 四、替换或修改「EFI分区」中的文件

如何修改和替换EFI

首先需要对「**ESP分区**」进行挂载：

#### WIN：

使用DG，默认挂载「**ESP分区**」，我们可以用DG工具对「**ESP分区**」中的**EFI**进行「**复制、删除、粘贴**」

PS:复制粘贴请使用快捷键：**Ctrl+C复制，Ctrl+V粘贴**

PS2：**替换EFI**：用DG删除「**ESP分区**」中的所有文件，然后将下载好的EFI复制粘贴在「**ESP分区**」目录下

#### MAC：

使用「**Clover Configurator**」进行挂载或使用「**命令符**」

打开终端，输入命令：**sudo diskutil mount disk0s1**或者**sudo diskutil mount EFI**

对「**EFI分区**」的文件进行复制、粘贴、删除

PS:替换EFI

**删除EFI分区的所有文件**，拷贝下载好的「**EFI**」到「**EFI分区**」

### 五、下载EFI

我制作了一系列的台式机的「**EFI**」，请查阅以下链接，

根据自己的配置类型选择下载合适的「**EFI**」，进行安装

适用于**6，7，8，9代CPU**的台式机安装教程：

https://github.com/Lubibest/Hackintosh

PS:下载好“**EFI-for-install**”并参考“**四、替换或修改EFI分区中的文件**”操作

其他机器：

https://github.com/daliansky/Hackintosh

### 六、安装OS

当你已经完成安装环境的部署、安装U盘的制作、以及「**EFI**」的修改或替换（或直接使用默认的EFI）后

你就可以开始进行安装了

#### （1)设置BIOS

你可以通过搜索工具搜索关于你的主板的BIOS设置

如果我的机器是微信B360，关键词<黑苹果微星B360BIOS>

PS:

**将你的硬盘模式调整为 AHCI** 

**开启支持 UEFI 启动**

**设置 你的 U盘为第一启动盘**

**快速启动-关闭**

**CFG-Lock-关闭**

**Secure Boot Mode-关闭**

**OS Type-Other OS**

**XHCI Handoff-Enabled，在USB控制器下可以找到**

**CSM模式-关闭**

**超级IO-关闭**

#### （2）选择「U盘启动」，进入「四叶草引导界面」

------选择**boot mojave install from install mojave**

------进入「**安装界面**」之后，选择「**语言**」

------进入「**磁盘工具**」，

对目标安装盘进行「**抹掉**」,

重命名卷名为"**Macintosh HD**"或其他

格式选择「**APFS**」

------关闭磁盘工具窗口

------选择「**安装Mojave**」

**PS：断开网络，拔掉以太网，断开wifi**

------安装将**重启多次**，选择**boot macos install from 「Macintosh HD」**或「抹盘的时候的卷名」

------安装完成，选择**boot macos from 「Macintosh HD」**或「抹盘的时候的卷名」

------安装完成

### 七、首次进入系统

PS:能跳过的尽量跳过

无法跳过：设置用户名及密码

### 八、进入桌面

### 九、将引导转移到硬盘

#### （1）挂载「EFI分区」

使用「**Clover Configurator**」进行挂载或使用命令符

---使用打开「**终端**」，输入命令：**sudo diskutil mount disk0s1**或者**sudo diskutil mount EFI**

#### （2）将U盘中的「EFI分区」「EFI目录」下的「BOOT」+「CLOVER」复制到「硬盘」的「EFI分区」「EFI文件」夹下

#### （3）重启,进BIOS设置，将硬盘设置为第一启动项

#### 完成

PS：下载好EFI-for-after install"并参考“四、替换或修改EFI分区中的文件”将EFI文件复制到U盘的EFI分区

### 注意事项：

安装过程如果遇到任何问题，请查阅黑果小兵的两篇教程,如下：

#### macOS Mojave 10.14安装中常见的问题及解决方法:

https://blog.daliansky.net/Common-problems-and-solutions-in-macOS-Mojave-10.14-installation.html

#### macOS 10.13安装中常见的问题及解决方法

https://blog.daliansky.net/macOS-10.13-installation-of-common-problems-and-solutions.html

----转载出处：黑果小兵部落阁，感谢黑果小兵daliansky

------

#### 本教程由

**垃圾帮主** 制作

**Genius-lbesT** 发布

并提供远程教学安装服务，如需远程技术支持，请添加我的QQ

作者：Genius-lbesT QQ2489050703

加入QQ群：724096369 黑苹果Genius
