---
title: add()
version: 2.1.0
signature: |
  moment.duration().add(Number, String);
  moment.duration().add(Number);
  moment.duration().add(Duration);
  moment.duration().add(Object);
---

通过增加时间来更改原始的时长。

用于创建时长的相同的键和速记可以在此处用作第二个参数。


```javascript
var a = moment.duration(1, 'd');
var b = moment.duration(2, 'd');
a.add(b).days(); // 3
```

注意，将无效的时长添加到任何其他时长会产生无效的时长。

