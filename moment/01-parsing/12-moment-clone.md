---
title: moment(Moment)
version: 1.2.0
signature: |
  moment(Moment);
---

所有的 moment 都是可变的。 
如果想要克隆 moment，则可以隐式或显式地操作。

在 moment  上调用 `moment()` 将会克隆它。

```javascript
var a = moment([2012]);
var b = moment(a);
a.year(2000);
b.year(); // 2012
```

此外，也可以调用 `moment#clone` 克隆 moment。

```javascript
var a = moment([2012]);
var b = a.clone();
a.year(2000);
b.year(); // 2012
```
