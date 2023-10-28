---
sidebar_position: 1
id: Config
---

# 配置文件

## options.yml

```yaml
# 无伤间隔/ 无敌帧
# 一个玩家打一次怪物 会有n tick 不能再伤害怪物
no-damage-ticks:
  disable-worlds:
  - example_world
  enable: true
  # tick
  value: 5
fight-status:
  enable: true
  # 战斗状态持续时间
  # tick
  value: 100
limit-damage-particle:
  max: 10
  enable: true
# 禁止直接普攻的材质
disable-attack-types:
  values:
  - BOW
  - CROSSBOW
compat-crack-shot:
  fight-groups:
    # 默认的战斗组 默认无，即FS不参与计算
    default: none
    Bazooka: attack-damage
    Carbine: attack-damage
  projectile-cache: true
attack-distance:
  distance-attack:
    # 距离攻击的特效
    effect: true
    # 距离攻击的声音
    sound: true
  # 默认攻击距离
  # 这里填原版的数值 建议不要改动
  # 如果有偏差会导致 “二次伤害” 的触发
  vanilla-distance:
    default: 3
    creative: 4.5
  # 攻击距离 单位为格
  enable: true
  value: '%as_att:AttackDistance%'
attack-cooldown:
  # 不冷却的材质
  no-cooldown-types:
  - BOW
  - CROSSBOW
  # 攻击冷却的时间与玩家原版攻击速度属性匹配
  enable: true
  # 最小蓄力值 若蓄力开启 且 蓄力值小于此值则伤害取消
  min-charge: 0.05
  # 任何时间都能攻击(冷却不结束，就不能攻击)
  # 伤害会被蓄力机制影响
  damage-any-time: true
  # cooldown 物品冷却
  # vanilla 原版攻击速度机制
  type: cooldown
  # 蓄力机制 (已度过冷却时间/总时间)
  charged: true
  # cooldown 基于物品冷却
  # vanilla 基于原版伤害
  charge-based: vanilla

```

## message.yml

```yaml
fight-message:
  action-bar:
    defend:
      text: '!&e&a{attacker-name} &e对你造成了: {message}'
      separator: '&5|'
    attack:
      text: '!&e你对 &a{defender-name} &e造成了: {message}'
      separator: '&5|'
    stay: 30
  chat:
    defend:
      text: '!&d[&9战斗系统&d] &e&a{attacker-name} &e对你造成了: {message}'
      separator: '&5,'
    attack:
      text: '!&d[&9战斗系统&d] &e你对 &a{defender-name} &e造成了: {message}'
      separator: '&5,'
  # AS的全息伤害显示
  # 支持动画
  # 纯发包不卡服务器
  holo:
    # 终止位置
    end:
      x: 0
      y: 1.5
      z: 0
    # 运动次数
    time: 15
    # 起始位置
    begin:
      x: 0
      y: 0.5
      z: 0
    # 存在时间
    stay: 20
  title:
    fade-out: 5
    defend:
      sub-title: '{message}'
      title: '{message}'
      separator: '&5|'
    attack:
      sub-title: '{message}'
      title: '{message}'
      separator: '&5|'
    fade-in: 3
    stay: 7
  # 默认的名字
  default-name:
    # attacker为null时
    attacker: 大自然
    # defender为null时
    defender: 未知
options:
  default:
    # ACTION_BAR ActionBar文本
    # CHAT 聊天框文本
    # DISABLE 关闭
    defend: chat
    # TITLE 标题
    # ACTION_BAR ActionBar文本
    # CHAT 聊天框文本
    # HOLO 全息文本
    # DISABLE 关闭
    attack: TITLE
    # 是否开启生命恢复全息提示
    # true 开启
    # false 关闭
    health-regain-holo: false
  # 是否开启玩家个性选择
  personal: true
# 生命恢复全息
health-regain-holo:
  distance: 8
  # 终止位置
  end:
    x: 0
    y: 1
    z: 0
  # 全息内容
  text: '&2+ &a{value}'
  # 运动次数
  time: -1
  # 起始位置
  begin:
    x: 0
    y: 1
    z: 0
  # 存在时间
  stay: 20

```

## slot.yml
### 这些都是attributesystem的东西,为了使用户看起来不乱，融合了一下
```yaml
#  2.1.0-beta 后已内置
#  "头盔": "HEAD"
#  "胸甲": "CHEST"
#  "护腿": "LEGS"
#  "靴子": "FEET"
#  "主手": "HAND"
#  "副手": "OFFHAND"
# 萌芽槽位
germ-slots:
- example
# 左AS内部槽位key 右原版槽位
#  2.1.0-beta 后已内置
#  "头盔": "HEAD"
#  "胸甲": "CHEST"
#  "护腿": "LEGS"
#  "靴子": "FEET"
#  "主手": "HAND"
#  "副手": "OFFHAND"
# 读取槽位20的装备 以20th为id存入装备栏
#  "20th": "20"
# 这样写可以给放到槽位的装备加限制:
#  "20th":
#    slot: 20
#    require: "槽位: 饰品"
entity: {}
# 左ID 右槽位
player: {}

```

## vaniila.yml
### 这些都是attributesystem的东西,为了使用户看起来不乱，融合了一下
```yaml
luck:
  enable: true
  value: '%as_att:Luck%'
  vanilla: true
# 支持 PAPI/PPAPI 字符串内联函数
# 会影响实体的原版属性 / 其它属性
# 支持任何原版属性，例如飞行速度FlySpeed
# fly-speed:
# enable: true
# vanilla: true
# value: %as_att:FlySpeed%
max-health:
  # 玩家默认血量
  default: 20
  enable: true
  value: '%as_att:MaxHealth%'
  vanilla: true
knockback-resistance:
  # 击退抗性
  enable: true
  value: '%as_att:Resistance%'
  vanilla: true
# 下面这些只支持玩家
attack-speed:
  # 单位为 攻击次数/s
  enable: true
  value: '%as_att:AttackSpeed%'
  vanilla: true
movement-speed:
  enable: true
  value: '%as_att:MovementSpeed% / 2250'
  vanilla: true

```
