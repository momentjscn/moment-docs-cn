---
title: 默认值
version: 2.2.1
signature: |
  moment("15", "hh")
---


可以创建一个 moment 对象，仅指定一些单位，其余的将会默认为当前的日期、月份、年份，小时、分钟、秒钟和毫秒默认为 0 。

当没传入任何值时，默认为现在时间：

```javascript
moment();  // 当前的日期和时间。
```

当仅传入小时、分钟、秒钟和毫秒时，默认为今天：
```javascript
moment(5, "HH");  // 今天 5:00:00.000
moment({hour: 5});  // 今天 5:00:00.000
moment({hour: 5, minute: 10});  // 今天 5:10.00.000
moment({hour: 5, minute: 10, seconds: 20});  // 今天 5:10.20.000
moment({hour: 5, minute: 10, seconds: 20, milliseconds: 300});  // 今天 5:10.20.300
```

当仅传入日期和更小的单位时，默认为本月和今年：

```javascript
moment(5, "DD");  // 本月的第 5 天
moment("4 05:06:07", "DD hh:mm:ss");  // 本月的第 4 天 05:06:07.000
```

如果未指定年份，则默认为今年：

```javascript
moment(3, "MM");  // 今年第三个月（三月）
moment("Apr 4 05:06:07", "MMM DD hh:mm:ss");  // 今年四月的第 4 天 05:06:07.000
```
