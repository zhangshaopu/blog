---
title: "Ubantu"
date: 2020-02-14T14:25:56+08:00
draft: false
tags: [ubantu]
categories: [tech,ubantu]
---
#  命令行软件包管理
##  一、APT
> 针对DPKG来说，它只能安装一个deb格式的包，同时会通知你安装这个包需要什么样的依赖，但是不会安装那些依赖文件，同时也对这个包进行配置，因为那些依赖包并没有下载安装。
> APT（或者是APT-GET) 是一个包管理系统(Package Management System) 。它不仅可以安装包本身，也可以将对应的依赖下载安装，并且配置他们。
    
    APT (Advanced Package Tool,高级软件包工具) 是一个强大的包管理系统，而那些图形化程序如 添加/删除 应用程序 和 Synaptic 都是建立在它的基础之上的。APT 自动处理依赖关系并在系统软件包执行其他操作以便安装所要的软件包。 运行 APT 要求管理权限 (参见 第1.3.3节 ― root 用户和 sudo 命令)。 

* 可以被 APT 使用的一些常用命令：
1. 安装软件包：
sudo apt-get install packagename
2. 删除软件包：
sudo apt-get remove packagename
3. 获取新的软件包列表：
sudo apt-get update
4. 升级有可用更新的系统：
sudo apt-get upgrade
5. 列出更多命令和选项：
apt-get help
有关 APT 用法的更多信息，请阅读全面的 Debian APT 用户手册。

## 二、使用 APTonCD 来安装软件包
> APTonCD可用来制作包含有您系统上所有软件包的CD，也可以制作包含的您选择的软件包或软件仓库的CD。在软件包管理器比如新立得中，找到aptoncd软件包并安装它。
更多有关 APTonCD 的文档可以在它的网站找到， aptoncd.sourceforge.net

* 安装单个软件包文件
  
安装程序的首选方式是通过本章所介绍的软件包管理器。然而，虽然 Ubuntu 软件包库非常大，但也有可能您想要安装的软件包并不在 Ubuntu 库中。如果这样的话，您也可以从网站下载并安装文件。 在您安装文件之前确认您所下载的文件来自一个安全的源是重要的。 有许多不同类型的 Linux 软件包文件。它们多数与特定 Linux 发行版的软件管理器相关联。如 Debian 软件包 文件 (.deb 文件)、Redhat 软件包管理器 文件 (.rpm 文件) 和 Tarballs (.tar 文件)。 本部分内容将介绍如何安装这些单个文件。 无法保证这些文件将与您系统兼容，如果您安装这些文件的话，您也将无法得到安全更新。有鉴于此，如果您想安装程序的话，请尽可能通过软件包管理器来安装由 Ubuntu 自身提供的应用程序软件包。
## 三、 安装/卸载 .deb 文件

* 这些是Debian 软件包。这些与 Ubuntu 相关的软件包文件使用 .deb 后缀是因为 Ubuntu 与 Debian GNU/Linux 发行版有着紧密的关系。您将需要管理权限来安装 .deb 文件 (参见 第1.3.3节 ― root 用户和 sudo 命令)。
* 要安装 .deb 文件，简单地双击它，然后选择 安装软件包 即可。或者，您也可以打开一个终端并输入：
sudo dpkg -i package_file.deb 来安装 .deb 文件。
如需卸载 .deb 文件，在您软件包管理器中反选它，或输入：
sudo dpkg -r package_name
## 四、 将 .rpm 文件转为 .deb 文件
    另一种软件包文件是 .rpm为后缀的 Red Hat 软件包管理器文件。我们并不建议在 Ubuntu 系统中安装它们。在绝大多数情况下，Ubuntu 自身的 .deb 软件包是可用的。然而，如果绝对必要，可以使用程序 alien 将 .rpm 文件转化为.deb 文件。
安装 alien 程序 (2 ― 添加、删除和更新应用程序)。
在终端使用管理权限运行以下命令：
sudo alien package_file.rpm
## 2.5.3. 安装 tarballs
    以 .tar.gz 或 .tar.bz2 作为后缀名的文件是在 Linux 和 Unix 中被广泛使用的 tarballs 的打包文件。 如果在任何 Ubuntu 软件库中都没有 Ubuntu 的软件包，您可以按照软件包自带的指示使用命令行来安装和卸载 Tarball 文件。 Tarballs 通常包括程序的源代码，并且需要 编译 才能使用。要做到这一点，一般需要其它软件 (参见 第3.8.1节 ― 基本编译器)。


# dpkg命令
dpkg常见用法： man dpkg
dpkg -i package.deb 安装包
dpkg -r package 删除包，不建议，不自动卸载依赖于它的包
dpkg -P package 删除包（包括配置文件）
dpkg -l 列出当前已安装的包，类似rpm -qa
dpkg -l package 显示该包的简要说明，类似rpm –qi
dpkg -L package 列出该包中所包含的文件，类似rpm –ql
dpkg -S \< pattern\> 搜索包含pattern的包，类似rpm –qf
dpkg -s package 列出该包的状态，包括详细信息，类似rpm –qi
dpkg --configure package 配置包，-a 使用，配置所有没有配置的软件包
dpkg -c package.deb 列出 deb 包的内容，类似rpm –qpl
dpkg --unpack package.deb 解开 deb 包的内容

dpkg示例：
列出系统上安装的所有软件包
dpkg -l
列出软件包安装的文件
dpkg -L bash
查看/bin/bash来自于哪个软件包
dpkg -S /bin/bash
安装本地的 .deb 文件
dpkg -i /mnt/cdrom/pool/main/z/zip/zip_3.0-11build1_amd64.deb
卸载软件包
dpkg -r zip
注意：一般建议不要使用dpkg卸载软件包。因为删除包时，依赖于它的其他任何包仍将安装，并且可能无法再正常运行

# apt
* Debian 使用APT工具来管理包系统，它与 rpm 命令不同。 在基于 Debian 的 Linux 发行版中，有各种工具可以与 APT 进行交互，以方便用户安装、删除和管理的软件包。
* apt-get 是其中一个常用的命令行工具，另外一款较为流行的命令行与 GUI 兼顾的工具是 Aptitude ，之前最常用的 Linux包管理命令都被分散在了 apt-get、 apt-cache和 apt-config 这三条命令中在 2014 年apt 命令发布第一个稳定版，Ubuntu 16.04 引入新特性之一便是 apt 命令，apt 命令解决了命令过于分散的问题，它包括 apt-get 命令出现以来使用最广泛的功能选项，以及 apt-cache 和 apt-config命令中很少用到的功能。在使用 apt 命令时，用户不必再由 apt-get 转到 apt-cache 或 apt-config，提供管理软件包所需的必要选项
* apt 相当于 apt-get、 apt-cache 和 apt-config 中最常用命令选项的集合
* apt 具有更精减但足够的命令选项，而且参数选项的组织方式更为有效。此外，启用的几个特性也非常有帮助。例如，可以在使用 apt命令安装或删除程序时看到进度条。
* apt 还会在更新存储库数据库时提示用户可升级的软件包个数
* apt 与 apt-get有一些类似的命令选项，但它并不能完全向下兼容 apt-get 命令,也即可用 apt 替换部分 apt-get 系列命令，但不是全部
