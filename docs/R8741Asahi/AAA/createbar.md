---
sidebar_position: 3
title: createBar
tags:
- Asahi
- 解释器列表
---

创建bar

- empty - 为空
- fill - 填充
- length - 长度
- percent - 百分比
---

# 基本用户

#### 基本格式

```yaml
set 强度条 = createBar [ empty to '&8|' , fill to '&a|' , length to 20 , percent to random 0 to 1 ]
```
#### 再或者，大括号版本
```yaml
set 强度条 = createBar {
  empty = '&8|'
  fill = '&a|'
  length = 20
  percent =  random 0 to 1
}
```
# 高级
#### 顺序:
- peek(["{", "["]) 

- questTypeMap()

因为是Map，所以参数可以不分先后顺序
