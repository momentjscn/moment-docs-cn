---
title: isMoment()
version: 1.5.0
signature: |
  moment.isMoment(obj);
---

要检查变量是否为 moment 对象，则使用 `moment.isMoment()`。

```javascript
moment.isMoment() // false
moment.isMoment(new Date()) // false
moment.isMoment(moment()) // true
```

从 **2.11.0** 版本开始，还可以通过 `instanceof` 运算符检测 moment 对象：


```javascript
moment() instanceof moment // true
```
