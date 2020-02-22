---
title: isDuration()
version: 1.6.0
signature: |
  moment.isDuration(obj);
---


要检查变量是否为 moment 的时长对象，则使用 `moment.isDuration()`。

```javascript
moment.isDuration() // false
moment.isDuration(new Date()) // false
moment.isDuration(moment()) // false
moment.isDuration(moment.duration()) // true
moment.isDuration(moment.duration(2, 'minutes')) // true
```
