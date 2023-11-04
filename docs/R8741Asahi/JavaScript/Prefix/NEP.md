---
sidebar_position: 3
title: next/expect/peek详解
id: NEP
---


- [点击进入AsahiLexer](https://doc.skillw.com/pouvoir/com/skillw/asahi/api/member/lexer/AsahiLexer.html)
- [初入茅庐](Prefix)


## **前言**
- 前面已经认识到了peek next，他们的区别主要是什么？
- expect又是什么？与peek next的区别是什么？

## **正文**

```javascript
lexer.next()
lexer.peek()
lexer.expect("eee")
```

---

### 什么是peek？

peek是查看，不是跳转

---

### 什么是next？

next是直接跳转到下一个token

---

### 什么是expect？

expect是直接寻求
```javascript
lexer.expect("eee")
```
这里的asahi如果下一个token为eee则返回true，如果不是false

**如果是eee则直接表示该token为空了，所以next会直接跳过该token，直接跳转到eee后面的token**

---

### 什么是token？

这边我给你讲一下asahi

**asahi("prefix 111 333 222")**

asahi其实是直接将里面的字符串改成

**[prefix, 111, 333, 222]这样一个数组**

然后匹配前缀解释器，中缀解释器等等

我的理解就是，数组里每一个元素的下标，就是token