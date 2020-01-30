---
title: isDST()
version: 1.2.0
signature: |
  moment().isDST();
---


`moment#isDST` 检查当前时刻是否为夏令时（daylight saving time）。

```javascript
moment([2011, 2, 12]).isDST(); // false, 2011年3月12日不是 DST。
moment([2011, 2, 14]).isDST(); // true, 2011年3月14日是 DST。
// 此示例适用于 "en" 语言环境：https://www.timeanddate.com/time/dst/2011.html
```

