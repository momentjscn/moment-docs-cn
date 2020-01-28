---
title: min()
version: 2.7.0
signature: |
  moment.min(Moment[,Moment...]);
  moment.min(Moment[]);
---

返回给定的 moment 实例的最小值（最远的过去）。

例如：

```javascript
var a = moment().subtract(1, 'day');
var b = moment().add(1, 'day');
moment.min(a, b);  // a
moment.min([a, b]); // a
```

不带参数的函数会返回带有当前时间的 moment 实例。

从 **2.10.5** 版本开始，如果其中一个参数是无效的 moment ，则结果为无效的 moment。

```javascript
moment.min(moment(), moment.invalid()).isValid() === false
moment.min(moment.invalid(), moment()).isValid() === false
moment.min([moment(), moment.invalid()]).isValid() === false
moment.min([moment.invalid(), moment()]).isValid() === false
```
