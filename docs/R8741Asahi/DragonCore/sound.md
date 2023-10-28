---
sidebar_position: 3
title: Sound
tags:
- Asahi
- 解释器列表
---

#### DragonPlaySound
- ##### 播放音效
- player - 玩家,不可忽略
- soundKey - 唯一Key,类似于UUID,默认值为随机的UUID,可以忽略
- soundFile - 音效路径,不可忽略
- volume - 音量,默认1.0,可以忽略
- pitch - 音高,默认1.0,可以忽略
- loop - 是否循环播放,默认false,可以忽略
- x - x轴
- y - y轴
- z - z轴
- xyz都不可忽略

#### DragonStopSound
- ##### 暂停播放
- Player - 玩家,不可忽略
- soundKey - 唯一key,不可忽略

---

# 基本用户

#### 基本格式
##### DragonPlaySound
```yaml
DragonPlaySound {
  player = $player
  soundKey = random 0 to 100
  soundFile = xxx/音效.ogg
  volume = 1.0
  pitch = 1.0
  loop = false
  x = 10.0
  y = 10.0
  z = 1.0
}
```
##### DragonStopSound
```yaml
DragonStopSound $player $UUID
```
# 高级
#### DragonPlaySound顺序:
- peek(["{", "["]) 

- questTypeMap()

因为是Map，所以参数可以不分先后顺序

#### DragonStopSound顺序
- questObj
- questString

有顺序,先Obj再String

