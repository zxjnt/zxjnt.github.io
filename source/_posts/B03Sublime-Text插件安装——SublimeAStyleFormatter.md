---
title: Sublime Text插件安装——SublimeAStyleFormatter
date: 2019-06-04 10:44:31
tags:
categories: [IT,Common]
---

本文将以SublimeAStyleFormatter插件为例来讲解Sublime Text插件的安装。

为什么需要安装插件呢？一些优秀的插件将帮助我们的编码工作变得简单，比如上面提到的SublimeAStyleFormatter插件能够实现代码的格式化。

如果没有格式化之前我们的代码可能是这样的：

```
#include <stdio.h>

int main(void)
{printf ("Hello World\n") ;
int sum =3+4;
return 0;}
```

格式化之后我们的代码应该是这样的：

```
#include <stdio.h>

int main(void)
{
    printf ("Hello World\n") ;
    int sum = 3 + 4;
    return 0;
}
```

好，下面进入正题，如何安装插件呢？

## 插件的安装

Step1:打开Sublime Text

Step2:同时按下 CMD + SHIFT + P

Step3:在弹出的窗口中输入“install”

Step4:光标选中“Package Control:Install Package”，按下回车键

Step5:在弹出的窗口中输入“SublimeAStyleFormatter”

Step6:选中SublimeAStyleFormatter，按下回车键，稍等一下，安装成功。

～到这儿Sublime Text其他插件的安装是不是也是so easy了


然而事情并没有那么顺利，在操作完 Step4 之后并不能成功看到 Step5 的弹窗，而是在漫长的等待后出现了一个弹框，有如下字样：

Package Control

There are no packages available for installation

Please see https://packagecontrol.io/docs/troubleshooting for help

悲剧了，国内的网络的环境总是不那么友好，那么首先你需要[学会科学上网](https://rubycoder.cn/2019/06/03/B02学会科学上网/)

一番折腾之后我们终于顺利安装了代码格式化的插件了，离成功还差最后的一小步，我们还需要做一些配置。

## Google C Style

当我们开始写第一行代码，我们就应该养成良好的代码习惯，那我们就遵守 Google 的代码风格吧。

Google的代码风格指南开源在<https://github.com/google/styleguide>，我们可以看到里面有多种语言的代码规范。我们现在学习的是 C，那就学习一下 C 的代码规范吧：[Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html)。啊！头大的英文，这儿帮大家找到了中文版 [Google 开源项目风格指南 (中文版)](https://zh-google-styleguide.readthedocs.io/)。

>注：中文版非官方，只是国内的一些大牛做的翻译，为了快速了解代码规范可以先看中文版，但最终请回归一级文献。

下面让我们来对SublimeAStyleFormatter做一些配置来更好的遵循Google Style吧

Step1:Sublime Text > Preferences > Package Settings > SublimeAStyleFormatter > Settings-Default

Step2:在打开的文档中找到options_default

Step3:分别做如下修改：    
"style": "google",      
"indent": "spaces",      
"indent-spaces": 4,       
"max-code-length": 200,        

Step4:CMD + S 保存，大功告成


代码格式化是如何操作的呢？

划重点====：CONTROL + OPTION + F

