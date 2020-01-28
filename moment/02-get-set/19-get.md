---
title: get()
version: 2.2.1
signature: |
  moment().get('year');
  moment().get('month');  // 0 至 11
  moment().get('date');
  moment().get('hour');
  moment().get('minute');
  moment().get('second');
  moment().get('millisecond');
---

字符串 getter。 
一般来说：

```javascript
moment().get(unit) === moment()[unit]()
```

单位不区分大小写，且支持复数形式和缩写形式：
year (years, y)、month (months, M)、date (dates, D)、hour (hours, h)、minute (minutes, m)、second (seconds, s)、millisecond (milliseconds, ms)。

