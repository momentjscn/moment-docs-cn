---
title: moment(Number[])
version: 1.0.0
signature: |
  moment(Number[]);
---


可以使用数值的数组（映射传给 [new Date()][JavaScript_Date] 的参数）来创建 moment。

`[year, month, day, hour, minute, second, millisecond]`

```javascript
moment([2010, 1, 14, 15, 25, 50, 125]); // February 14th, 3:25:50.125 PM
```

年份之后的任何值都是可选的，并且默认为可能的最小值。

```javascript
moment([2010]);        // January 1st
moment([2010, 6]);     // July 1st
moment([2010, 6, 10]); // July 10th
```

使用数组的构造将会在当前时区中创建一个日期。 
若要从 UTC 数组创建日期，则使用 `moment.utc(Number[])`。

```javascript
moment.utc([2010, 1, 14, 15, 25, 50, 125]);
```

注意：因为这映射了原生的 `Date` 参数，所以月份，小时，分钟，秒钟、毫秒都是从零索引的。 
每月的年和日是从1开始索引。

这通常是混乱的原因，尤其是月份，因此请注意！

如果数组代表的日期不存在，则 `moment#isValid` 将会返回 false。

```javascript
moment([2010, 12]).isValid();     // false（不是真实的月份）
moment([2010, 10, 31]).isValid(); // false（不是真实的日期）
moment([2010, 1, 29]).isValid();  // false（不是闰年）
```
