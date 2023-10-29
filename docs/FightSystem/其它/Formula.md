---
sidebar_position: 1
id: Vanilla
---
# 公式系统

## 介绍

通过**公式系统**，你可以完成各种**复杂的计算**，以带入到各个地方

## 配置文件

> plugins/AttributeSystem/vaniila.yml

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

## 调用

#### 用户

变量`%as_formula:公式id%`

#### 开发者

```kotlin
AttributeSystem.formulaManager.get(entity,"max-health")
```
