---
sidebar_position: 1
title: 下载
id: asahi
---


- [点击进入](https://github.com/q210520993/Javascript-about-Minecraft)

### 介绍

ItemSystem 是由 Glom-c 所开发的基于 Taboolib Pouvoir 的物品库插件,由强大的群友修复而成如今Asahi版本
本页会为你提供几十种Asahi前缀解释器用于你的服务器

Asahi与Kether的共同之处?

    极其类似的语法

    极其相似的空格的格式,极为难懂(我原称之为脑掺格式)

优点?

    优化好,比kether好很多

    支持JavaScript拓展前缀解释器

缺点?

    作者高三行动不便,很少有人可以维护,除非有逆天群友,我们都称这类群友成仙了

    BUG有点多,所以最多用于计算等,千万别当脚本用了

接下来我所说的每一个前缀解释器拓展组,他们都有自己各自的命名空间,他们的命名空间就是他们的拓展组名
```yaml
    使用前请在你的脚本下添加一行using [ DragonCore ]

    所谓using便是lang命名空间下的,可以在你的asahi脚本中添加命名空间

    你可以直接在命名空间中添加DragonCore,不使用using
    
    值得注意的是using也是一个前缀解释器,他所在的命名空间是lang,哪为什么他不需要导入?
        - 因为lang和common前缀解释器都是默认的,他们都是直接存在于asahi脚本里的
```
---

对于一些可扩展API，**Pouvoir** 提供了脚本拓展

并使用脚本注解进行自动注册注销

#### Asahi 前缀解释器拓展 (Asahi Prefix Parser Extension)

```javascript
//@AsahiPrefix(-name example)
/*
    值得注意的是,result上面并没有context,所以位置不能颠倒
    每一行的quest都是先后执行的
    你可以试试做一个代码块处理quest
    例如
    const quest = (function() {
        if(lexer.peek() == "[" || lexer.peek() == "{") return lexer.questTypeMap()
        return null
    })()
*/
function example(lexer) {
    var numberQuester = lexer.questDouble()
    return result(function (context) {
        var number = numberQuester.get(context)
        print(number)
        return number
    })
}
```