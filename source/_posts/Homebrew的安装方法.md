---
title: Homebrew的安装方法
date: 2019-06-03 09:44:12
tags:
categories: [IT]
---

## 关于Homebrew
Homebrew是一款Mac OS平台下的软件包管理工具，拥有安装、卸载、更新、查看、搜索等很多实用的功能。简单的一条指令，就可以实现包管理，而不用你关心各种依赖和文件路径的情况，十分方便快捷。

Homebrew官网 <https://brew.sh>

通过官网介绍我们可以知道安装Homebrew只需要简单的在控制台键入一行命令即可。

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

然而，事情并没有那么简单。在国内的网络环境下经常安装失败，如何解决呢？请看下文：

## 国内镜像安装
### 下载安装脚本文件
下载 <https://raw.githubusercontent.com/Homebrew/install/master/install>

另存为文件名，比如命名为：brew_install，存储在Download目录下。

### 修改安装脚本
修改 brew_install文件, 替换成清华大学的镜像，具体如下：

找到如下代码：

```
BREW_REPO = "https://github.com/Homebrew/brew".freeze
```

更改为：

```
BREW_REPO = "https://mirrors.ustc.edu.cn/brew.git".freeze
```

### 执行安装脚本

```
ruby brew_install
```

> 注意：brew_install的执行路径，还记得上面存储在哪个目录的吗？

如果此时脚本应该停在

```
==> Tapping homebrew/core

Cloning into '/usr/local/Homebrew/Library/Taps/homebrew/homebrew-core'...
```

出现这个原因是因为源不通，代码来不下来，解决方法是：要么使用科学上网，要么更换国内镜像源(中科院的镜像)，运行下面的命令：

```
git clone git://mirrors.ustc.edu.cn/homebrew-core.git/ /usr/local/Homebrew/Library/Taps/homebrew/homebrew-core --depth=1
```

然后把homebrew-core的镜像地址也设为中科院的国内镜像，运行下面的命令：

```
cd "$(brew --repo)"
git remote set-url origin https://mirrors.ustc.edu.cn/brew.git
cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
git remote set-url origin https://mirrors.ustc.edu.cn/homebrew-core.git
```

### 检查brew是否安装成功

```
brew update
brew doctor
```