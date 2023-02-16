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
### Entity操作

#### **location**
获取实体位置
```yaml
&entity location #获取实体位置
```
#### **teleport**
传送实体
```yaml
&entity teleport to 目标(Location / Entity)
```
#### **name**
获取实体名字
```yaml
&entity name
```
#### **displayName**
获取实体显示名字
```yaml
&entity displayName
```
#### **velocity**
获取/修改实体速度
```yaml
&entity velocity #获取实体速度
&entity velocity to 向量(Vector) #设置实体速度
```
#### **metadata**
获取/修改实体[MetaData](https://jd.bukkit.org/org/bukkit/metadata/Metadatable.html)

MetaData是一种存储临时数据(关服、退服后会消失)的可选方案
```yaml
&entity metadata key(String) #返回实体特定key下的MataDataValue
&entity metadata key(String) to value(MetaDataValue) #返回实体特定key下的MataDataValue
```
#### **fireTicks**
获取/修改实体燃烧时间，以tick为单位
```yaml
&entity fireTicks #获取实体燃烧时间
&entity fireTicks to 时间(Int) #设置实体燃烧时间
```
#### **fallDistance**
获取/修改实体摔落距离
```yaml
&entity fallDistance #获取实体摔落距离
&entity fallDistance to 时间(Int) #设置实体摔落距离
```
### LivingEntity操作

#### **health**
获取/修改实体生命值
```yaml
&entity health #获取实体生命值
&entity health to 血量(Int) #设置实体生命值
```
#### **maxHealth**
获取/修改实体最大生命值
```yaml
&entity maxHealth #获取实体最大生命值
&entity maxHealth to 血量(Int) #设置实体最大生命值
```
#### **potion**
给实体药水效果[XPotion](https://github.com/TabooLib/taboolib/blob/501ad4cb34a2b6bc8cb5302f30fe1b824eb80706/platform/platform-bukkit/src/main/java/taboolib/library/xseries/XPotion.java)
```yaml
&livingEntity potion add 药水(XPotion)
```
#### **nearbyEntities**
获取周围以实体为中心的一个碰撞箱内的实体

x y z 为碰撞箱各坐标轴上长度的1/2
```yaml
&livingEntity nearbyEntities x(Double) y(Double) z(Double)
```
#### **rayHitEntity**
获取实体视线方向的实体
```yaml
&livingEntity rayHitEntity 距离(Double)
```
### Location操作

#### **toVector**

```yaml
&location 
```
#### **distance**

```yaml
&location 
```
#### **direction**

```yaml
&location 
```
#### **multiply**

```yaml
&location 
```
#### **length**

```yaml
&location 
```
#### **clone**

```yaml
&location 
```
#### **world**

```yaml
&location 
```
#### **pitch**

```yaml
&location 
```
#### **yaw**

```yaml
&location 
```
#### **x**

```yaml
&location 
```
#### **y**

```yaml
&location 
```
#### **z**

```yaml
&location 
```
#### **add**

```yaml
&location 
```
#### **subtract**

```yaml
&location 
```
#### **zero**

```yaml
&location 
```


### Vector操作

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