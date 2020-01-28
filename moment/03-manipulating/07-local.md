---
title: local()
version: 1.5.0
signature: |
  moment().local();
---

在原始的 moment 上设置标记，以使用本地时间（而不是原始的 moment 时间）显示 moment。

```javascript
var a = moment.utc([2011, 0, 1, 8]);
a.hours(); // 8 UTC
a.local();
a.hours(); // 0 PST
```

也可以用于转换出固定的偏移模式：

```javascript
moment.parseZone('2016-05-03T22:15:01+02:00').local().format(); // "2016-05-03T15:15:01-05:00"
```

有关 UTC 模式的更多信息，参阅 [moment.utc()][moment.utc]。

