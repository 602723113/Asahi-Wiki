---
sidebar_position: 1
title: Namespace-Lang
tags:
- 解释器列表
---

# Lang命名空间

## 前缀解释器
---
### 基础语法

#### **null**
顾名思义，返回null
#### **pass**
返回空字符串 ""
#### **布尔值**
true,false
#### **return**
设定函数返回值
#### **exit(stop)**
执行退出程序回调函数
#### **代码块**
代码块用{}包裹
#### **命名空间导入**
using 命名空间数组 导入指定命名空间

`using [ bukkit , regex ]`

unusing 命名空间 移除指定命名空间，用于防止语句冲突

`unusing regex`

### 函数

#### **fun(def)**
顾名思义，声明函数
~~(伟大的圆括号!)~~
```yaml
fun callDamage ( amount player ) = {

   damage &entity &amount by &player 

}
```

#### **invoke(call)**
顾名思义，调用函数
```yaml
fun main = {

    invoke callDamage [ 60 , &player ]

}
```


#### **import**

导入其它脚本文件的上下文

路径似乎是一种相对路径: 类似这样 /plugins/Pouvoir/scripts/test.asahi

```yaml
import [ /plugins/Pouvoir/scripts/test.asahi , /plugins/BuffSystem/scripts/test2.asahi ]
```

### 变量

#### **set**
顾名思义，设置变量
```yaml
#set 变量名 =(to) 值
set neige = "南山道人"
#set 变量名 ifdef =(to) 值  如果变量已存在就不重新定义，并返回已存在的值
set glom ifdef = "咕咕咕"
#set 变量名 by lazy =(to) 代码块  类似Kotlin中的 by lazy 只有在获取时才执行代码块中的内容并取值
set zimaBlue by lazy = {
  print "诗远"
  return "紫马布鲁"
}

```
#### **has**
顾名思义，看看有没有这个变量
#### **get**
顾名思义，取出这个变量
#### **delete**
顾名思义，删除这个变量
```yaml
if has glom then {
  get glom
  delete glom
}
```

### 流程控制-条件

#### **if**
if都不会用就紫砂吧
```yaml
if check 1 < 2 then {
  print "1显然小于2"
} else {
  print "数学不存在了"
}
```
#### **condition**

#### **switch(when)**
```yaml
print switch of "Glom" {
  case == "Glom" -> "咕咕咕"
  else -> "Glom!"
}
```

### 流程控制-循环

#### **_label_**
任何循环都可以加入label(标签)用于标识循环
```yaml
#这里如果不写标签，break就会产生歧义
repeat 1 with index label "outer" then {
  while check &entity health > 0 label "inner" then {
    damage &entity 1
    if check &entity velocity == 0 then {
      break "inner"
    }
  }
}
```
#### **while**
```yaml
while check &entity health > 0 then {
  damage &entity 1
}
```
#### **repeat**
指定循环间隔，并提供循环次数
repeat 间隔 with 次数变量
```yaml
repeat 1 with index label "outer" then {
  print "循环，第 ${&index} 次"
}
```
#### **for(foreach)**
用于遍历集合
```yaml
set array = [ "唧唧复唧唧" , "木兰当户织" , "问女何所思" , "问女何所忆" ]
for poem in array then {
  print &poem
}
```
### 数字操作

abs 值(Number)

ceil 值(Double) 向上取整

floor 值(Double) 向下取整

round 值(Double) 四舍五入取整

format 值(Number) 格式(String) 格式化数字 格式类似"#.##"

max 值 to 值 返回二者之间的最大值

min 值 to 值 返回二者之间的最小值

max 值数组 返回数组中最大值

min 值数组 返回数组中最大值

range 值(Double) to/~/.. 值(Double)  返回一个范围

number 值 将值转换为数值
### 数学运算
三角函数名 值(弧度制)

sin cos tan asin acos atan 

对数函数名 底数值 值

log 3 9

ln 9 

lg 10

log2 8
### 随机数
#### **random**
random 值(Double) to 值(Double)

randomInt 值(Int) to 值(Int)

randomObj 值(List) 从集合里随机取一个元素

#### **weight**
带权重随机

weight [ 权重(Int) to 值 , 权重(Int) to 值 ] 直接取出随机后的值

weight [ 权重(Int) to 值 , 权重(Int) to 值 ] build 类似lazy，返回taboolib.common5.RandomList 需要取值时调用其random函数 ~~(这玩意有什么意义...)~~
```yaml
print weight [ 10 to "Glom" , 20 to "Neige" , 20 to "紫马布鲁" ]

```

### Java对接

#### **java**
导包
```yaml
#从包package中获取所有的Class，之后用Class名调用
java in com.skillw.pouvoir.util
#获取单个class
java of com.skillw.pouvoir.util.EntityUtil
```

#### **new**
实例化一个类
```yaml
new ItemStack ( Material.AIR )
```

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
#### 