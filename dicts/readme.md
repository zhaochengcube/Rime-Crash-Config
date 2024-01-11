# 词库

以下是各文件夹所包含词库的说明。

## clover

四叶草基础词库

## extend

原扩展词库，主要来源于网络~~其实就是搜狗啦~~

## thuocl

清华大学 yyds

## other

字面意思

放了中文维基词库

```yaml
import_tables: # 不需要的加'#'即可
  # clover
  - dicts/ice/8105 # 雾凇拼音，字表
  - dicts/ice/41448 # 大字表
  - dicts/clover/clover.base # 单字，四叶草
  - dicts/ice/base # 基础词库
  - dicts/ice/ext # 扩展词库
  - dicts/clover/clover.phrase # 词组
  # other
  # - dicts/luna_pinyin # 从 luna_pinyin.dict.yaml 导入包含单字的码表
  - dicts/other/zhwiki # 中文 wiki（较大，卡顿建议注释）
  # - dicts/other/zhwiki.ipcjs # 中文 wiki @ipcjs fork 版（较大，卡顿建议注释），转换成繁体，进行多音字注音，只保留3字及以上的词组，去除重复词条
  - dicts/other/myemoji # emoji 颜文字
  # thuocl
  - dicts/thuocl/THUOCL_IT # 本词表包含了大量IT类词汇，THU Open Chinese Lexicon
  - dicts/thuocl/THUOCL_caijing # 本词表包含了大量财经类词汇
  - dicts/thuocl/THUOCL_chengyu # 本词表包含了大量成语词汇
  - dicts/thuocl/THUOCL_diming # 地名
  # extend
  - dicts/extend/luna_pinyin.wenhua # 成语、诗词、文言
  - dicts/extend/luna_pinyin.sogoupopular # 网络流行新词，搜狗
  # - dicts/extend/luna_pinyin.chaizi # 简体拆字
  # - dicts/extend/luna_pinyin.cn_en # 中英混输
  # - dicts/extend/luna_pinyin.hanyu # 汉语扩充
  - dicts/extend/luna_pinyin.computer # 计算机
  # - dicts/extend/luna_pinyin.zhejiang # 浙江信息
  # - dicts/extend/luna_pinyin.yanwenzi # 颜文字
  # - dicts/extend/luna_pinyin.game # 游戏，DND，MC，RA，魔兽争霸
  - dicts/extend/luna_pinyin.changyong # 常用聊天用语
  - dicts/extend/luna_pinyin.zhuanye # 专业术语，地理，法律，军事，天文，物理，数学
  # - dicts/extend/luna_pinyin.extra_hanzi # 额外的字
  # - dicts/extend/luna_pinyin.english # 英语
  - dicts/extend/luna_pinyin.sgmain # @scomper 做的搜狗词汇汇总
```