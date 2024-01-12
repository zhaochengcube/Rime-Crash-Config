# 效果预览：

## Mac：
<div align="center"><img src="https://gitlab.com/zhaochengcube/images/-/raw/main/pictures/2024/01/11_20_32_46_rime-mac.png" width="" height="" /></div>

## Win：
<div align="center"><img src="https://gitlab.com/zhaochengcube/images/-/raw/main/pictures/2024/01/11_20_46_53_rime-win.png?ref_type=heads" width="" height="" /></div>

## 英文输入
<div align="center"><img src="https://gitlab.com/zhaochengcube/images/-/raw/main/pictures/2024/01/11_21_41_55_rime-en.png" width="" height="" /></div>

--- 

# 前言
Rime的全名是：中州韵输入法引擎，也就是说它不是一个具体的输入法，而是一个可以随意扩展定制的输入法框架。并且它免费、开源、跨平台，最重要的一点是数据本地化，词库和配置看得见，摸得着。本文不对Rime做过多介绍，如果对其感兴趣可以去[官网](https://rime.im/)了解更多。

本文旨在对Rime的Mac或Windows10/11端的快速配置并快速上手使用，下面我将说明该如何使用。

# 使用
首先在[官网](https://rime.im/)下载Rime，Windows下载小狼毫(Weasel)，Mac下载鼠鬚管(Squirrel)，然后下载本仓库代码。

## Mac
Mac用户下载好后默认的配置文件夹为：`~/Library/Rime`，也可以通过 “系统输入法菜单/鼠鬚管/用户设置打开” ，注意：Mac用户下载好后需要重新登录或者重启才能生效。打开配置文件夹和下载好的本仓库代码，将除`weasel.custom.yaml`以外的文件全复制到配置文件夹中。复制完成后，点击 “系统输入法菜单/鼠鬚管/重新部署”，首次部署大约要20秒左右，部署期间敲键盘输出的是英文，部署好后再敲就会正常显示了。

## Win
Win用户下载后的默认配置文件夹为：`%APPDATA\Rime%`，也可以通过 “任务栏\小狼毫输入法\用户文件夹打开” ，最好安装的时候选择自己指定的文件夹，Win用户不需要重新登录，打开配置文件夹和下载好的本仓库代码，将除`squirrel.custom.yaml`以外的文件全复制到配置文件夹中。复制完成后，点击 “任务栏\小狼毫输入法\重新部署”，首次部署大约要20秒左右，部署期间敲键盘输出的是英文，部署好后再敲就会正常显示了。

--- 
总结下来就是：
1. 下载本仓库文件
2. 找对配置文件目录
3. 按要求无脑复制到配置文件目录
4. 重新部署，输入启动！

# 配置说明
默认配置有：
- 小鹤双拼、明月全拼和Easy_en英文输入法
- 默认按`shift`切换中英文
- 按`Ctrl+Shift+Space`打开输入法切换框
- 默认的候选框是横向的

如果你不想折腾或者目前的配置就足够你使用了，下面的内容就不用再读了。

## 配置更改
切记：更改任何配置后，一定要重新部署！！！
### 候选框改为垂直
打开对应系统Rime用户文件夹内的，Mac：`squirrel.custom.yaml`, Win: `weasel.custom.yaml`这个文件，将`horizontal`的值改为false即可。
### 修改皮肤
还是打开刚刚那个文件，修改`color_scheme`的值，其值取决去该文件内定义的预设主题，比如：`apathy`,`mojave_dark`等，你也可以自己写主题。
### 自定义词典
我这里默认配置了词组，在`dicts`文件夹中，这里面的词组都是其他大佬做的，所以最好不要动，但我们可以维护自己的词典。打开`mydicts.dict.yaml`这个文件，文件如下图所示：
<div align="center"><img src="https://gitlab.com/zhaochengcube/images/-/raw/main/pictures/2024/01/11_21_23_51_rime-dict.png" width="" height="" /></div>

在`...`标记后另起一行即是我们自己配置的码表(词典)，码表通过制表符(Tab)分割为三个部分：文字，编码，权重。

文字即时敲击编码后展示的文字，如果编码有多个音节，各个音节以空格分开，权重越大，出现在候选框中的位置越靠前。切记：中间两个一定要是Tab，不能是空格！！！

### 自定义符号
对应配置文件：`mysymbols.yaml`，在这里配置全角，半角以及符号，符号的配置参考[雾凇拼音](https://github.com/iDvel/rime-ice)，注意配置符号串的时候开头字母一定要是大写V

### Lua脚本集成
本配置默认集成了日期脚本，输入`date`会显示当前日期的大写和小写，输入`time`会显示当前时间

### 参考博客
- https://www.dreamxu.com/install-config-squirrel/
- https://jiz4oh.com/2020/10/how-to-use-rime/
- https://sspai.com/post/84373
- https://dvel.me/posts/rime-ice/
