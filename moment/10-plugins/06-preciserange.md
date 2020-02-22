---
title: precise-range
signature: |
  npm install moment-precise-range-plugin
---

由 [Rob Dawson][codebox] 编写的 [Precise Range][moment-date-range-plugin] 插件可用于显示日期/时间范围的准确的人类可读的表示形式：

```javascript
moment("2014-01-01 12:00:00").preciseDiff("2015-03-04 16:05:06");
 // 1 year 2 months 3 days 4 hours 5 minutes 6 seconds
```

```javascript
moment.preciseDiff("2014-01-01 12:00:00", "2014-04-20 12:00:00");
// 3 months 19 days
```

要获取原始数字值而不是字符串，则将 `true` 值作为第三个参数传给该方法：

```javascript
moment.preciseDiff(m1, m2, true); 
// {years : 0, months : 1, days : 2, hours : 3, minutes : 4, seconds : 5, firstDateWasLater : false}
```
