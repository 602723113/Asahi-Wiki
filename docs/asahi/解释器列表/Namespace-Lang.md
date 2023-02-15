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
`fun callDamage ( amount player ) = {
   damage &entity &amount by &player 
}`
#### **invoke(call)**
顾名思义，调用函数
`fun main = {
    invoke callDamage [ 60 , &player ]
}`
#### **import**
## 中缀解释器
---
### Java对接

#### 