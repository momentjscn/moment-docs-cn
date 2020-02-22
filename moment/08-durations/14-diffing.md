---
title: duration(x.diff(y))
version: 2.1.0
signature: |
  var duration = moment.duration(x.diff(y))
---

可以将时长与 `moment#diff` 一起使用，以获取两个时刻之间的时长。 
为此，只需将 `moment#diff` 方法传给 `moment#duration`，如下所示：

```javascript
  var x = new moment()
  var y = new moment()
  var duration = moment.duration(x.diff(y))
  // 返回时长对象，其时长在 x 和 y 之间。
```

参阅[此处][moment.diff]以获取有关 `moment#diff` 的更多信息。

