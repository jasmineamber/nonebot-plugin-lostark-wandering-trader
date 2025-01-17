<!--
 * @Author         : EmiyaGm
 * @Date           : 2023-8-2 10:37:25
 * @Description    : None
 * @GitHub         : https://github.com/emiyagm
-->

<p align="center">
  <a href="https://v2.nonebot.dev/"><img src="https://v2.nonebot.dev/logo.png" width="200" height="200" alt="nonebot"></a>
</p>

<div align="center">

# nonebot-plugin-lostark-wandering-trader

_✨ NoneBot 命运方舟国服流浪商人刷新时间查看 自动播报稀有及其以上卡牌刷新 插件 ✨_

</div>

<p align="center">
  <a href="https://raw.githubusercontent.com/emiyagm/nonebot-plugin-lostark-wandering-trader/main/LICENSE">
    <img src="https://img.shields.io/github/license/emiyagm/nonebot-plugin-lostark-wandering-trader.svg" alt="license">
  </a>
  <a href="https://pypi.python.org/pypi/nonebot-plugin-lostark-wandering-trader">
    <img src="https://img.shields.io/pypi/v/nonebot-plugin-lostark-wandering-trader.svg" alt="pypi">
  </a>
  <img src="https://img.shields.io/badge/python-3.8+-blue.svg" alt="python">
</p>

## 重要提示
~~因为国服更新了韩服最近的流浪商人机制，已经不再需要提示了，所以本插件暂停更新~~

嘿嘿，我又回来了，突然发现还是有必要做个提示的，毕竟只是间隔6个小时，所以我针对性的做了修改，删除了下一个商人这个功能，增加了商人情况这个功能，会告知当前有无商人出现，防止大家记不住

## 安装

```bash
nb plugin install nonebot_plugin_lostark_wandering_trader
```
或者
```bash
pip install nonebot-plugin-lostark-wandering-trader
```

## 更新

```bash
nb plugin update nonebot_plugin_lostark_wandering_trader
```
或者
```bash
pip install nonebot-plugin-lostark-wandering-trader -U
```

### 导入插件
- 在`pyproject.toml`里的`[tool.nonebot]`中添加`plugins = ["nonebot_plugin_lostark_wandering_trader"]`

**注**：如果你使用`nb`安装插件，则不需要设置此项

## 使用方式

通用:

- 发送 Command `商人情况` 获取某个服务器当前有无商人，有商人的话则返回持续出现的时间
- 每隔x分钟会自动通报稀有度在蓝色以上的卡片刷新位置

## 配置项

配置方式：直接在 NoneBot 全局配置文件中添加以下配置项即可。

### TRADER__USER_IDS

- 类型：`list`
- 默认值：`[]`
- 说明：需要发送通知的QQ号（需要是好友）

### TRADER__GROUP_IDS

- 类型：`list`
- 默认值：`[]`
- 说明：需要发送通知的群号（需要在群里）

### TRADER__TIME

- 类型: `int`
- 默认: `1`
- 说明: 检测流浪商人位置结果间隔时间

### TRADER__RARITY

- 类型: `list`
- 默认值: `[]`
- 说明: 需要通告的卡牌的稀有度，如果不填或是空，则默认会将 Rare 稀有度包括 Rare 以上的卡牌都通告
  - Rare : 蓝色
  - Epic : 紫色
  - Legendary : 橙色

### TRADER__SEND_TYPE

- 类型: `list`
- 默认值: `[]`
- 说明: 需要通告的内容，如果不填或是空，则默认会将卡牌以及橙色的礼物都通告
  - Card : 卡牌
  - Rapport : 礼物

### TRADER__SERVER_ID

- 类型: `int`
- 默认: `14`
- 说明：服务器对应的id（参考如下）：
  - 先锋服务器（亚克拉西亚）: 1
  - 先锋服务器（先锋体验服）: 2
  - 卢佩恩（卢特兰）: 3
  - 卢佩恩（安忆谷）: 4
  - 卢佩恩（妮娜芙）: 5
  - 卢佩恩（卡丹）: 6
  - 卢佩恩（希里安）: 7
  - 卢佩恩（摩可可）: 12
  - 卢佩恩（塞卡）: 13
  - 卢佩恩（艾弗格雷斯）: 14
  - 卢佩恩（纳西尼尔）: 15
  - 卢佩恩（凯萨尔）: 16
  - 卢佩恩（洛恒戴尔）: 17
  - 卢佩恩（库克赛顿）: 19
  - 卡杰洛斯（贝隆）: 23
  - 卡杰洛斯（巴尔坦）: 24
  - 卡杰洛斯（贝拉）: 25
  - 卡杰洛斯（阿尔古斯）: 26
  - 卡杰洛斯（艾达琳）: 27
  - 卡杰洛斯（特里希温）: 28
  - 卡杰洛斯（凯因）: 29
  - 卡杰洛斯（卡隆）: 30
  - 普罗提温（托托克）: 31
  - 普罗提温（阿布莱修德）: 32
  - 普罗提温（艾伦）: 33
  - 普罗提温（阿贾娜）: 34
  - 普罗提温（萨沙）: 35
  - 普罗提温（卡门）: 36
  - 普罗提温（阿黛尔）: 37
  - 普罗提温（霸者之剑）: 38

配置文件示例（默认模板）

```dotenv
TRADER__USER_IDS=[12345678,87654321]
TRADER__GROUP_IDS=[12345678,87654321]
TRADER__TIME=1
TRADER__SERVER_ID=14
TRADER__RARITY=["Rare","Epic","Legendary"]
```

## 说明

数据来源：https://www.emrpg.com