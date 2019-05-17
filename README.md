# 100-series-hackintosh

##### 作者：**Genius-lbesT** QQ2489050703

##### 加入QQ群：724096369 黑苹果Genius

本教程制作为**6代hd530**核显台式机CPU通用的安装及完善驱动.

#### ·适用于hd630的200系(100系）的主板请阅读

##### （PS：200系主板的教程同样适用于搭载7代CPU的核显为HD630的100系主板）

##### https://github.com/Lubibest/200-series-hackintosh-mojave

#### ·适用于uhd630的300系主板的请阅读：

##### https://github.com/Lubibest/300-series-hackintosh-mojave



## 正文

##### AMD / NVDIA / INTEL均可通过EFI-for-install.zip安装到机器上.

EFI蓝本为黑果小兵daliansky博客 blog.daliansky.net 的镜像with clover 4903（nvdia)/clover 4928(AMD+INTEL)提取.

NVDIA支持10.13.6/AMD+INTEL支持最新版本mojave10.14.5

感谢黑果小兵daliansky

#### AMD+INTEL-Mojave 10.14.5

镜像下载：https://blog.daliansky.net/macOS-Mojave-10.14.5-18F132-official-version-with-Clover-4928-original-image.html

#### AMD+INTEL-Mojave 10.14.4

镜像下载： https://blog.daliansky.net/macOS-Mojave-10.14.4-18E226-official-version-with-Clover-4903-original-image.html

#### Nvdia-High Sierra 10.13.6

镜像下载：https://blog.daliansky.net/macOS-High-Sierra-10.13.6-17G65-Release-Version-with-Clover-4596-original-mirror.html



### 一、安装教程

https://github.com/Lubibest/How-to-install-a-Hackintosh

### 二、安装

#### 1.AMD显卡

AMD免驱显卡推荐安装mojave10.14.5，镜像下载地址：

https://blog.daliansky.net/macOS-Mojave-10.14.5-18F132-official-version-with-Clover-4928-original-image.html

安装教程：https://github.com/Lubibest/How-to-install-a-Hackintosh

用**clover configurator**替换U盘的**ESP分区**的EFI文件为**EFI-for-after install-AMD.zip**

重启生效

AMD显卡的机器将持续得到clover升级的支持

### 2.intel

Intel HD530 核显推荐安装mojave10.14.5

镜像下载地址：

https://blog.daliansky.net/macOS-Mojave-10.14.5-18F132-official-version-with-Clover-4928-original-image.html

安装教程：https://github.com/Lubibest/How-to-install-a-Hackintosh

用clover configurator替换U盘的ESP分区的EFI文件为EFI-for-after install-intel.zip  

PS：intel注入为0X12345678,请查阅核显ID列表查找并尝试驱动或通过Hackintool注入补丁，本教程为对核显机器完善驱动。

intel的机器将会持续得到clover升级的支持

#### 3.NVDIA显卡的机器

nvdia显卡推荐安装10.13.6（17G65)，镜像下载地址：

https://blog.daliansky.net/macOS-High-Sierra-10.13.6-17G65-Release-Version-with-Clover-4596-original-mirror.html

安装教程：https://github.com/Lubibest/How-to-install-a-Hackintosh

请在安装完成后使用终端运行下面的命令，并用clover configurator替换U盘的ESP分区的EFI文件为EFI-for-after install-nvdia.zip

bash <(curl -s https://raw.githubusercontent.com/Benjamin-Dobell/nvidia-update/master/nvidia-update.sh)

重启生效

由于nvdia显卡无法更新os版本，我将不再为nvdia显卡的机器更新clover。

如需要技术支持，请加我的QQ

### 三、本教程中已放入applealc.kext，请根据自己的声卡型号尝试注入声卡ID，声卡ID请查阅下面这篇教程：

AppleALC支持的Codecs列表及AppleALC的使用

https://blog.daliansky.net/AppleALC-Supported-codecs.html

常用ALC：

alc 887  注入 5/7

alc 892  注入 1/2

a1220    注入 1/2

s1220a   注入 1/2

注入位置：

clover configuratoer

Devices/Audio/inject(手动输入）

![](https://github.com/Lubibest/300-series-hackintosh-mojave/blob/master/appleALC.png)

### 四、注意事项：

安装过程如果遇到任何问题，请查阅黑果小兵的两篇教程,如下：

#### macOS Mojave 10.14安装中常见的问题及解决方法:

https://blog.daliansky.net/Common-problems-and-solutions-in-macOS-Mojave-10.14-installation.html

#### macOS 10.13安装中常见的问题及解决方法

https://blog.daliansky.net/macOS-10.13-installation-of-common-problems-and-solutions.html

### 五、本教程适用的主板包括

微星H110,微星b150,微星Z170

技嘉H110,技嘉B150,技嘉Z170

华硕H110,华硕B150,华硕Z170

或

H110,B150,Z170芯片组的台式机电脑

具体请自行测试。

如有疑问，请添加QQ：2489050703 Genius-lbesT

### 六、AMD显卡的EFI将在后续的os版本升级中得到更新

### 七、本教程EFI

由

**-垃圾帮主-**修改制作

**-Genius lbesT-**发布

并提供远程教学安装服务，如需远程技术支持，请添加我的QQ

作者：**Genius-lbesT** QQ2489050703

加入QQ群：724096369 **黑苹果Genius**
