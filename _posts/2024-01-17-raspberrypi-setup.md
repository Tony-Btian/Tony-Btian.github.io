---
layout: post
title: 玩转 Raspberry Pi (树莓派)
subtitle: Raspberry Pi (树莓派) 基本使用手册
author: 翰宝
header-img: img/post-bg-raspberrypi-setup.jpg
header-mask: 0.4
tags:
  - 嵌入式系统
  - RaspberryPi
  - 资料
  - 树莓派
---

> Raspberry Pi 由英国的 Raspberry Pi Foundation 开发，是一款高性能单板计算机。其尺寸小，成本低，使它迅速成为DIY爱好者、制造者、电子爱好者以及专业开发者中非常受欢迎的嵌入式设备。

# Raspberry Pi 的硬件配置
---
Raspberry Pi 因其可扩展性、功能性和成本效益而成为一个非常受欢迎的设备，不仅适用于初学者和学生，也适用于专业人士。
- 电源
- 

## 树莓派型号对比




# Raspberry Pi OS 系统写入
---
写入前的准备
硬件：
- SD卡
- SD 卡读卡器

软件：
- 树莓派系统写入工具：[Raspberry Pi Imager](https://www.raspberrypi.com/software/)

将 SD 卡用读卡器连接电脑，打开树莓派写入工具，选择合适的 Raspberry Pi 型号和系统，以及 SD 存储卡。系统选择最好选择发布时间最近的 Raspberry Pi OS，一般会有推荐系统。Debian 的硬件支持更好，所以这里以 Debian 系统为例。

![[/img/in-post-imag/post-inner-raspberry-pi-imager.png]]

烧录完成后，直接将 SD 卡插入 Raspberry Pi 即可。通电后，系统会自动初始化，加载。通过简单的系统引导配置，就可以进入系统了。如果有外界显示设备，可以通过 HDMI 连接外部显示设备。

> 每次系统烧录都会格式化 SD 卡，因此在烧录之前需要备份好 SD 卡中的数据

系统操作界面如下所示：

# 远程连接 Raspberry Pi
---
## SSH 连接

SSH 是一种加密的远程连接网络协议，其主要用于远程管理系统和服务器。SSH 连接通过公钥加密来确保两台设备之间传输的数据是安全且保密的。建立连接后，SSH 通过命令行执行指令，如果连接对象是 Linux 系统，则直接用终端指令即可对远程设备进行控制。

在 Raspberry Pi 中开启 SSH 连接的方法有两种：
- 从图形界面进行设置
- 通过命令行进行设置

**从图形界面进行设置**



**通过命令行进行设置**

在终端中输入

```Shell
sudo raspi-config
```

选择 `5 Interface Options` -> `SSH` 开启 SSH

## VNC 连接

VNC 连接

# Raspberry Pi 连接后的第一件事
---
## 更新系统

```Shell
sudo apt-get update
sudo apt-get upgrade
```

首次更新系统一般需要花费很长的时间。