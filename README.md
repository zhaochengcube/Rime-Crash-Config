## 前言
Rime的全名是：中州韵输入法引擎，也就是说它不是一个具体的输入法，而是一个可以随意扩展定制的输入法框架。并且它免费、开源、跨平台，最重要的一点是数据本地化，词库和配置看得见，摸得着。本文不对Rime做过多介绍，如果对其感兴趣可以去[官网](https://rime.im/)了解更多。

本文旨在对Rime的Mac、Windows10/11、Android和IOS端的基本配置（基于[oh-my-rime](https://www.mintimate.cc/)最新配置并添加了Easy_en英文输入和部分词库）

## 安装
首先在[官网](https://rime.im/)下载Rime，Windows下载小狼毫(Weasel)，Mac下载鼠鬚管(Squirrel)，安装部分可以参考[oh-my-rime](https://www.mintimate.cc/)的教程。安装好后打开Rime的用户配置文件地址，默认的配置文件地址如下：

- MacOS `$HOME/Library/Rime/`
- Windows `%APPDATA%/Rime`
- Android Fcitx(小企鹅) `Android/data/org.fcitx.fcitx5.android/files/data/rime/`

Mac和Win用户也可以通过软件打开配置文件地址，在系统任务栏找到Rime图标后右键点击“用户设定”或“用户文件夹”即可。

## 导入配置

下载本仓库文件并复制到Rime的配置目录内，同样在系统任务栏找到Rime图标后右键点击重新部署，首次部署大约一分钟左右。

###  配置说明

- 集成[oh-my-rime](https://www.mintimate.cc/)所有配置
- 增加了Easy_en英文输入法和部分词库

- 按`shift`切换中英文
- 按`Ctrl+Grave(破浪键)`打开输入法切换框
- 输入候选分离且候选框是横向的
- 配色方案为碧皓青

### 配置更改

切记：更改任何配置后，一定要重新部署！！！

#### 外观展示

![image](https://www.mintimate.cc/image/demo/themeOfOhMyRime.webp)

详细见[不同操作系统展示效果 | oh-my-rime输入法](https://www.mintimate.cc/zh/demo/diffAppearance.html)

#### 自定义激活的输入法

修改`default.custom.yaml`文件，按照格式修改就行，修改时注意缩进！

``````yaml
schema_list:
    - schema: double_pinyin_flypy # 小鹤双拼
    - schema: rime_mint # 薄荷拼音
    - schema: rime_mint_flypy # 薄荷拼音-小鹤混输方案
    - schema: easy_en # 英文输入
    # - schema: terra_pinyin         # 地球拼音-薄荷定制
    # - schema: wubi98_mint          # 五笔98-五笔小筑
    # - schema: wubi86_jidian        # 五笔86-极点86
    # - schema: t9                   # 仓九宫格-全拼输入
    # - schema: double_pinyin_abc    # 智能ABC双拼
    # - schema: double_pinyin_mspy   # 微软双拼
    # - schema: double_pinyin_sogou  # 搜狗双拼
    # - schema: double_pinyin_ziguang # 紫光双拼
    # - schema: double_pinyin         # 自然码双拼
``````

如果要增加额外的输入方案，比如现在要增加云龙国际音标，下载了相关的`ipa_yunlong.schema.yaml`schema文件，只需要在上面`schema_list`下增加`- schema: ipa_yunlong`即可。

#### 自定义词典
打开`dicts/custom_simple.dict.yaml`这个文件，文件如下图所示：
<div align="center"><img src="https://gitlab.com/zhaochengcube/images/-/raw/main/pictures/2024/01/11_21_23_51_rime-dict.png" width="" height="" /></div>

在`...`标记后另起一行即是我们自己配置的码表(词典)，码表通过制表符(Tab)分割为三个部分：

- 文字，输入编码后出现的候选
- 编码，输入的字母或组合(音节)
- 权重，决定“文字”在候选中出现的位次，越大则越靠前

如上图所示，连续敲“oo”，第一个候选项会出现“哦哦”。现在新建一个词典项，比如：

- 安静	an jing	9999 多个音节用空格隔开
- 茕茕孑立  qqjl  1

切记：中间两个分隔符一定要是Tab，不能是空格！！！实测添加一个词典项后重新部署的时间10秒左右。

如果你有很多词组要添加，可以新建词典配置文件，文件命名要求：自定义.固定(dict.yaml)，比如添加一个：`mydicts2.dict.yaml`，文件内容要求如上，你可以按照你的习惯组织你整理的若干词典文件。

打开配置文件夹下的`rime_mint.dict.yaml`文件，在`import_tables`下添加你的词典文件，添加的时候文件名的固定部分可以省略，比如：`- mydicts2`，有目录的话也要加上目录前缀。

要注意的是这个`rime_mint.dict.yaml`文件中的配置顺序会影响候选出现的位次，因为不同词典文件可能出现相同权重的词典项，配置越上优先级越高。

## 相关链接

- https://www.mintimate.cc/
- https://github.com/rime/weasel/wiki
- [https://github.com/rime/squirrel/wiki/squirrel.yaml-%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97](https://github.com/rime/squirrel/wiki/squirrel.yaml-配置指南)
- https://sspai.com/post/84373
- https://dvel.me/posts/rime-ice/
- https://sspai.com/post/79469
- https://sspai.com/post/88595
