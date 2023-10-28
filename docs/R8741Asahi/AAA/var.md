---
sidebar_position: 2
title: var / const / let
tags:
- Asahi
- 解释器列表
---

定义变量，与`set`的区别是

- 只能在`物品生产流程`中使用
- 若已经有此变量名的变量，则跳过定义
- 变量值会自动保存到物品 NBT，供自动更新/重新构建物品时使用


---

# 基本用户
#### 基本格式

```yaml
set 强度条 = createBar [ empty to '&8|' , fill to '&a|' , length to 20 , percent to random 0 to 1 ]
```
# 高级
#### 顺序:
- next()

- expect(["to", "="])

- questAny()
