---
sidebar_position: 3
title: Namespace-bukkit
tags:
- Asahi
- 解释器列表
---

# Bukkit命名空间

## 前缀解释器
---

## 中缀解释器
---

### Player操作

#### **actionbar**
给玩家发送actionbar信息(解析颜色)
```yaml
&player actionbar 信息(String)
```
#### **title**
给玩家发送title信息(解析颜色)
```yaml
&player title 大标题(String) 小标题(String) 淡入(Int) 持续(Int) 淡出(Int)
```
#### **message**
给玩家发送message信息(解析颜色)
```yaml
&player actionbar 信息(String)
```
#### **messages**
给玩家发送一系列message信息(解析颜色)
```yaml
&player actionbar 信息(List<String>)
```
#### **command**
以玩家身份执行命令
```yaml
&player command 指令(String)
```
#### **allowFlight**
获取/设置玩家是否可飞行
```yaml
&player allowFlight #返回玩家是否可飞行
&player allowFlight to 值(Boolean) #设置玩家是否可飞行
```
#### **bedSpawn**
获取/设置玩家床重生点的位置
```yaml
&player bedSpawn #返回玩家床重生点
&player bedSpawn to 值(Location) #设置玩家床重生点
```
#### **blocking**
获取玩家是否在用盾牌格挡
```yaml
&player blocking
```
#### **cooldown**
获取/设置玩家特定物品的冷却

由于原版限制，同一玩家同一材质的物品冷却共享
```yaml
&player cooldown 材质(Material) #返回玩家特定物品的冷却
&player cooldown 材质(Material) to 冷却(Int) #设置玩家特定物品的冷却
```
#### **name**
获取玩家名字
```yaml
&player name
```
#### **healthScale**
获取/设置玩家血量压缩
```yaml
&player healthScale #返回玩家血量压缩
&player healthScale to 值(Int) #设置玩家血量压缩
```
#### **isSneaking**
获取玩家是否在潜行
```yaml
&player isSneaking
```
#### **isSleeping**
获取玩家是否在睡觉
```yaml
&player isSleeping
```
#### **exp**
获取/设置玩家经验
```yaml
&player exp #返回玩家经验
&player exp to 值(Int) #设置玩家经验
```
#### **level**
获取/设置玩家原版等级
```yaml
&player level #返回玩家原版等级
&player level to 值(Int) #设置玩家原版等级
```
#### **playSound**
给玩家播放特定音效

volume 是音量大小 pitch 是音调高低
```yaml
&player playSound 音效(Sound) with volume(Float) pitch(Float)
```
#### **stopSound**
终止玩家特定音效的播放
```yaml
&player stopSound 音效(Sound)
```
#### **metadata**
获取/修改玩家[MetaData](https://jd.bukkit.org/org/bukkit/metadata/Metadatable.html)

MetaData是一种存储临时数据(关服、退服后会消失)的可选方案
```yaml
&player metadata key(String) #返回玩家特定key下的MataDataValue
&player metadata key(String) to value(MetaDataValue) #返回玩家特定key下的MataDataValue
```
### Vector操作

```yaml

```
#### **rotateAroundX**

```yaml

```
#### **rotateAroundY**

```yaml

```
#### **rotateAroundZ**

```yaml

```
#### **toLocation**

```yaml

```
#### **normalize**

```yaml

```
#### **isNormalized**

```yaml

```
#### **isInSphere**

```yaml

```
#### **isInAABB**

```yaml

```
#### **midpoint**

```yaml

```
#### **dot**

```yaml

```
#### **divide**

```yaml

```
#### **distance**

```yaml

```
#### **crossProduct**

```yaml

```
#### **copy**

```yaml

```
#### **angle**

```yaml

```
#### **multiply**

```yaml

```
#### **length**

```yaml

```
#### **clone**

```yaml

```
#### **x**

```yaml

```
#### **y**

```yaml

```
#### **z**

```yaml

```
#### **add**

```yaml

```
#### **subtract**

```yaml

```
#### **zero**