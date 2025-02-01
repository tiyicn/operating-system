# 替换为国内版
```shell
curl -sSL https://os-artifacts.smart-assistant.cn/os -o /mnt/data/os && sh /mnt/data/os
```
## 下载：[Operating-System(操作系统)](https://github.com/tiyicn/operating-system/releases)
# [📚 文档](DOCS.md)

# Home Assistant 操作系统

Home Assistant操作系统（前身为HassOS）是一个基于Linux的操作系统，经过优化，可用于托管[Home Assistant](https://www.home-assistant.io)及其[附加组件](https://www.home-assistant.io/addons/).

Home Assistant操作系统使用Docker作为其容器引擎。默认情况下，它将家庭助理主管部署为容器。家庭助理主管反过来使用Docker容器引擎来控制单独容器中的家庭助理核心和附加组件。Home Assistant操作系统不是基于像Ubuntu这样的常规Linux发行版。它是使用[Buildroot](https://buildroot.org/)构建的并且它被优化为运行Home Assistant。它针对Raspberry Pi或ODROID等单板计算（SBC）设备，但也支持具有UEFI的x86-64系统。

[![Home Assistant - A project from the Open Home Foundation](https://www.openhomefoundation.org/badges/home-assistant.png)](https://www.openhomefoundation.org/)

## 特点

- 重量轻，内存高效
- 最小化I/O
- 空中下载（OTA）更新
- 离线更新
- 使用Docker容器引擎进行模块化

## 支持的硬件

- 纳布之家
- 树莓派
- 硬核ODROID
- 华硕Tinker Board
- 通用x86-64（例如英特尔NUC）
- 虚拟设备

请参阅完整列表和具体型号[此处](./Documentation/boards/README.md)

## 入门指南

如果你只想使用Home Assistant官方的[入门指南](https://www.home-assistant.io/getting-started/)和[安装说明](https://www.home-assistant.io/hassio/installation/)带您了解如何下载Home Assistant操作系统并使其在您的计算机上运行。

如果你有兴趣了解更多关于家庭助理操作系统及其工作原理的信息，请阅读。。。

## 发展

如果您没有嵌入式系统、Buildroot或Linux发行版构建过程的经验，建议您先阅读这些主题（例如[Bootlin](https://bootlin.com/docs/)拥有丰富的资源）。

Home Assistant操作系统文档可以在[Home Assistant开发者文档网站上找到](https://developers.home-assistant.io/docs/operating-system).

### 组件

- **引导程序：**
- [GRUB](https://www.gnu.org/software/grub/)适用于支持UEFI的设备
- [U引导](https://www.denx.de/wiki/U-Boot)适用于不支持UEFI的设备
- **操作系统：**
- [构建根](https://buildroot.org/)LTS Linux
- **文件系统：**
- [SquarshFS](https://www.kernel.org/doc/Documentation/filesystems/squashfs.txt)对于只读文件系统（使用LZ4压缩）
- [ZRAM](https://www.kernel.org/doc/Documentation/blockdev/zram.txt)对于“/tmp”、“/var/”和swap（使用LZ4压缩）
- **集装箱平台：**
- [Docker引擎](https://docs.docker.com/engine/)用于在容器中运行Home Assistant组件
- **更新：**
- [RAUC](https://rauc.io/)用于空中下载（OTA）和USB更新
- **安全：**
- [AppArmor](https://apparmor.net/)Linux内核安全模块

### 开发建设

开发构建GitHub操作工作流是一个手动触发的工作流
其创建家庭助理OS开发构建。开发版本为
可在[https://os-artifacts.home-assistant.io/index.html](https://os-artifacts.home-assistant.io/index.html).
