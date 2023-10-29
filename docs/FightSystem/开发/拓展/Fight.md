---
sidebar_position: 1
id: FightDev
---

# 触发战斗机制组

见[`FightSystem`](https://doc.skillw.com/attsystem/com/skillw/attsystem/api/AttributeSystemAPI.html)

前者会解析战斗信息并发送，后者则不会
调用时会运行**机制组**，返回的是**运行结果**(伤害)
之后你需要**手动对实体造成伤害**

例:

> JavaScript

```javascript
const FightData = com.skillw.fightsystem.api.fight.FightData;
const result = com.skillw.fightsystem.api.runFight(
  "test-fight",
  new FightData(attacker, defender),
  true //是否计算战斗信息并发送
);
//造成伤害，如果你是异步，那么记得要同步调用
//同步调用: task(function(t){defender.damage(result,attacker)})
defender.damage(result, attacker);
```

或

> Kotlin

```kotlin
val result = com.skillw.fightsystem.api.runFight(
  "test-fight",
  FightData(attacker, defender)
){
    //初始化战斗数据
  }
//造成伤害，如果你是异步，那么记得要同步调用
defender.damage(result, attacker);
```

# 特殊情况

在**抛射物**造成伤害的情况下，伤害的**计算开始于命中**时，

这就导致了玩家可以通过抛射一个物体，再快速换装备以**达到更大伤害的目的**

可惜的是，因为机制组的特性，我们无法再正常运行机制组，只能对公式做运算

为了避免这种情况，我们可以这么做:

> JavaScript

```javascript
const FightData = com.skillw.fightsystem.api.fight.FightData;
function runDamage(attacker) {
  var formula = "{伤害公式}";
  //                         只填攻击者
  const data = new FightData(attacker, null);
  formula = data.handle(formula);
  //省略
  //当命中实体时
  const defender = entity;
  //设置命中的实体
  data.defender = defender;
  const result = data.handle(formula);
  defender.damage(result, attacker);
}
```
