---
title: subtract()
version: 2.1.0
signature: |
  moment.duration().subtract(Number, String);
  moment.duration().subtract(Number);
  moment.duration().subtract(Duration);
  moment.duration().subtract(Object);
---

通过减去时间来更改原始的时长。

用于创建时长的相同的键和速记可以在此处用作第二个参数。

```javascript
var a = moment.duration(3, 'd');
var b = moment.duration(2, 'd');
a.subtract(b).days(); // 1
```

注意，将无效的时长添加到任何其他时长会产生无效的时长。

