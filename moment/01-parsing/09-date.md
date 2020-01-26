---
title: moment(Date)
version: 1.0.0
signature: |
  moment(Date);
---


可以使用预先存在的原生 Javascript Date 对象来创建 `Moment`。

```javascript
var day = new Date(2011, 9, 16);
var dayWrapper = moment(day);
```

这会克隆 `Date` 对象，`Date` 的后续更改不会影响 `Moment`，反之亦然。
