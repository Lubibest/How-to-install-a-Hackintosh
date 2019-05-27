# 如何隐藏启动项

#### 前言：

当我们将EFI的主要配置都完善之后，我们发现启动四叶草的时候，显示了除了我们需要使用的启动mac/win10之外的好几个启动项，我们如果在clover中隐藏他呢？

阅读本文，你会找到方法。

### 一、挂载EFI

1）使用命令符挂载：

打开终端，输入命令：**sudo diskutil mount disk0s1**或者**sudo diskutil mount EFI**

2）使用**CLOVER CONFIGURATOR**挂载

### 二、修改config.plist

1、使用**CLOVER CONFIGURATOR**打开EFI/CLOVER/config.plist，选择GUI标签页

2、取消勾选传统方式的引导Legacy选项，目标位置GUI/Scan/Legacy

3、GUI/Hide Volume下，添加Preboot+Recovery

![](https://github.com/Lubibest/How-to-install-a-Hackintosh/blob/master/How%20to%20hide%20volume/hide%20volime.png)

### 三、保存-重启生效



## 四、本教程由

**垃圾帮主**修改制作

**Genius lbesT**发布

作者：**Genius-lbesT**

qq群：724096369

![](https://github.com/Lubibest/Hackintosh/blob/master/JPG/QQ.png)

 **黑苹果Genius**   [打赏](https://github.com/Lubibest/About-Genius-lbesT)
