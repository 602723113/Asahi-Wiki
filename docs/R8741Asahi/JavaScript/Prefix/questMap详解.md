---
sidebar_position: 2
title: questTypeMap
id: questTypeMap
---


- [点击进入AsahiLexer](https://doc.skillw.com/pouvoir/com/skillw/asahi/api/member/lexer/AsahiLexer.html)
- [初入茅庐](Prefix)

#### Asahi 前缀解释器拓展 (Asahi Prefix Parser Extension)

```javascript
//@AsahiPrefix(-name createBar -namespace common)
function testfun(lexer) {
  const quest = (function() {
    if(lexer.peek() == "[" || lexer.peek() == "{") return lexer.questTypeMap()
    return null
  })()
  return result(function (context){
    const empty = isNull(quest.get(context).get("empty"), "&7|")
    const fill = isNull(quest.get(context).get("fill"), "&a|")
    const length = isNull(quest.get(context).get("length"), 20)
    const percent = isNull(quest.get(context).get("percent"), 0.0)
    return createBar.createBar(empty, fill, length, percent)
  })
}
```

:::info

这是我写的一个**createBar**前缀解释器，一般人可能会直接questList

但这样其实十分麻烦，对于user来说，一个固定的值一个固定的位置，是不友好的

可以尝试questTypeMap这个东西，不过我有一个统一的格式，就是

```javascript
  const quest = (function() {
    if(lexer.peek() == "[" || lexer.peek() == "{") return lexer.questTypeMap()
    return null
  })()
```
这样quest有什么好处呢？

有效防止[ {被识别为其他quest的对象

因为是个map，所以quest.get(context)得到的是一个Map，输出是{xxx: xxx, ......}的一段map，要怎么取值？
直接get(key)

:::

为什么选择Map而不是List？

好吧我直白的说一下

写这种东西用List在asahi中看起来是**一坨史**，非常难读，让人一眼看上去，**史**！