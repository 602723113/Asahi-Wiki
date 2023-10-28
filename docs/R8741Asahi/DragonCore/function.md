---
sidebar_position: 2
title: function
tags:
- Asahi
- 解释器列表
- 龙核
---
#### 基本参数
- player - 玩家,不可忽略
- GuiName - Gui的名字,不可忽略
- function - 方法名,不可忽略
- isAsync - 是否异步执行,默认true,可以忽略
```yaml
何为异步执行?可以理解为我的世界主线程运行,可以大大提高运行性能,但是必须是安全的情况下可以使用,比如扣血这种就不可以使用异步,会报错,一些东西异步可能会直接卡线程,直接把服务器卡死,所以慎用。
```
---

# 基本用户
#### 基本格式

```yaml
DragonRunFunction {
    player = $player
    GuiName = 张德摔大哥
    function = 王九十二弟
    isAsync = false
}
```
# 高级
#### 顺序:
- peek(["{", "["]) 

- questTypeMap()

因为是Map，所以参数可以不分先后顺序
