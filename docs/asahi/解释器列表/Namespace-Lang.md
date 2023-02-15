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
  print("诗远")
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

### 流程控制

#### **if**

#### **condition**

#### **switch(when)**

#### **while**

#### **repeat**

#### **for(foreach)**

### 数学运算

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

#### 