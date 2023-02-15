---
sidebar_position: 2
title: Namespace-common
tags:
- 解释器列表
---

## 前缀解释器
---

## 中缀解释器
---
### Java对接
#### **Array操作**
```yaml
array get at 0 
array set at 0 to "Minecraft"
array length #返回数组长度
```
#### **List操作**
```yaml
list get at 索引
list set 索引 值
list add 值 #给list添加元素
list addAll 值(List) #合并list
list remove at 索引
list remove 值 #查找并删除值，只删一个

list length #返回list长度
list size #返回list大小
list isEmpty #是否为空

list toArray
list toString

list merge by 值(String) 将list值以特定分隔符连接为字符串

```

#### **Map操作**
```yaml
map get 值(key)
map put(set) 值(key) to 值(value)
map putAll 值(Map) #合并map
map remove 值(key)
map contains 值(key)
map size
map keys
map values
map entries
```

#### **Pair操作**
```yaml
pair key
pair value
```

#### **[CompletableFuture](https://www.liaoxuefeng.com/wiki/1252599548343744/1306581182447650)操作**
```yaml
future join #等待结束
```