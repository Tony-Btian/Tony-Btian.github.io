---
layout: post
title: 在 Raspberry Pi 上使用 Git
subtitle: Raspberry Pi 的 Git 简单教程
author: 翰宝
header-img: img/post-bg-git.jpg
header-mask: 0.4
tags:
  - Git
  - RaspberryPi
  - 树莓派
  - 嵌入式系统
---

> Raspberry Pi 中没有像在 Windows 中与 Github Desktop 简单好用的 Git 的软件，如果有 Git 需求，就只能通过命令行。

# 简介
---
在使用 Raspberry Pi 进行项目开发时，需要能够实时调用 Raspberry Pi 的 GPIO 硬件资源，这使得直接在 Raspberry Pi 的编程环境中进行开发成为了最方便快捷的选择。然而 Raspberry Pi 中没有像 Windows 当中那样简单好用的 Github Desktop，为了满足版本控制和联合开发的需求，学习 Git 命令行才是正道。

在这个教程中，将介绍如何在 Raspberry Pi 上安装和使用 Git。Git 是一个强大的版本控制工具，它允许个人和团队对相同的项目进行联合开发，同时也能高效地管理项目的不同版本。

Raspberry Pi 作为一个经济实惠且功能强大的小型计算机，非常适合用于嵌入式项目的学习和开发，而嵌入式的开发离不开版本控制。通过这个教程，希望能让读者能够学会如何配置 Git 环境，如何使用 SSH 公钥和私钥对，如何创建一个新的 Git 仓库，以及执行基本的 Git 操作，提交更改，推送到远程仓库等。

# 在 Raspberry Pi 上安装 Git
---
在 Raspberry Pi 上安装 Git 非常简单，只需运行下面的指令：
```bash
sudo apt install git
```

### 设置 Git
告诉 Git，是谁在进行操作。由于 Git 可能有多个人进行开发，所以在 Git 版本控制的过程中，需要告诉对方谁修改了文件。
```bash
git config --global user.name "Name"
git config --global user.email "username@email.com"
```

设置默认的文本编辑器。告诉 Git 你喜欢哪一种文本编辑器。这里推荐使用 `nano`
```bash
git config --global core.editor nano
```

# 生成 SSH 密钥对
---
SSH 密钥通常用于远程服务器的登陆，也可以用于 Github 这样的 Git 仓库服务进行安全通信。而生成和使用 “SSH 密钥对” 的目的是为了方面访问例如 Github 的在线仓库，避免频繁使用 “用户名” 和 “密码” 登陆。

### 生成 SSH 密钥
