---
title: 输入法切换到Rime
date: 2019-10-23
categories:
  - 工具
---

QQ 拼音终于也开始弹广告了，所以一怒之下准备删了。

又不能没输入法用，就用上了小狼毫。记录一下这中间遇到的若干坑。

<!-- more -->

## 安装

一路下一步，唯一的坑在于`自定义用户文件夹`这个功能。**不要设置自定义用户文件夹**。

如果是为了 rime 的多平台同步，rime 有另一个同步功能可以进行同步，而不需要同步整个用户文件夹。

rime 有一个包管理器，但是这个包管理器在 windows 上并不能正确的识别用户文件夹：无论用户怎么设置，包管理器都会认为用户文件夹在默认的`%APPDATA%/rime`。而用包管理器所安装的包也只会放到那个文件夹里面，而小狼毫则是从用户设置的自定义文件夹中加载配置。这样一来，包管理器完全无法工作。

## 同步

同步 rime 有一个自带的同步功能，也就是安装完后看到的`【小狼毫】用戶資料同步`开始菜单选项。

首先打开用户文件夹中的`installtion.yaml`（我就不介绍 yaml 语法了）
，添加一个`sync_dir`选项指向你想要同步的位置，比如我设置的是`$OneDrive/rime`，那么在点击同步之后，rime 会在`$sync_dir`文件夹下新建一个文件夹，名为这个文件里面的`id`一项（这一项你也是可以改的，比如我改成了`windows`），然后把你这台机器里面的所有配置和和词库同步过去。

如果 rime 在这个文件夹下面还找到了其他机器的同步结果，他还会合并其他机器的词库，所以只要定时的让小狼毫自动同步，就能解决多台机器的同步问题。

## To Be Continued

## 设置

所有的设置都是 yaml 选项

设置：

1. 候选词数量
2. 双拼
3. 双拼时不显示全拼码
4. 导入词库
5. 设置问题
