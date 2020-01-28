---
title: set()
version: 2.2.1
signature: |
  moment().set(String, Int);
  moment().set(Object(String, Int));
---

通用 setter，接受单位作为第一个参数、值作为第二个：

```javascript
moment().set('year', 2013);
moment().set('month', 3);  // 四月
moment().set('date', 1);
moment().set('hour', 13);
moment().set('minute', 20);
moment().set('second', 30);
moment().set('millisecond', 123);

moment().set({'year': 2013, 'month': 3});
```

单位不区分大小写，且支持复数形式和缩写形式：
year (years, y)、month (months, M)、date (dates, D)、hour (hours, h)、minute (minutes, m)、second (seconds, s)、millisecond (milliseconds, ms)。

对象解析新增于 **2.9.0**。
