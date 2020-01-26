---
title: moment(Number)
version: 1.0.0
signature: |
  moment(Number);
---


与 `new Date(Number)` 类似，可以通过传入一个整数值来创建 moment，该整数值表示自 Unix 纪元（1970 年 1 月 1 日 12AM UTC）以来的毫秒数。

```javascript
var day = moment(1318781876406);
```

[注意：ECMAScript 将此称为“时间值”][sec-time-values-and-time-range]。

