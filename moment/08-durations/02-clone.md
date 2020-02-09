---
title: clone()
version: 2.19.0
signature: |
  moment.duration().clone();
---

创建时长的副本。 
时长是可变的，就像 moment 对象一样，因此可以在某个时间点获取快照。

```javascript
var d1 = moment.duration();
var d2 = d1.clone();
d1.add(1, 'second');
d1.asMilliseconds() !== d2.asMilliseconds();
```
