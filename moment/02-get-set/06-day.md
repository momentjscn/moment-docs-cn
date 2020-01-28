---
title: day()
version: 1.3.0
signature: |
  moment().day(Number|String);
  moment().day(); // 数字
  moment().days(Number|String);
  moment().days(); // 数字
---

获取或设置星期几。

此方法可用于设置星期几，其中星期日为 0、星期六为 6。

如果给定的值是 0 到 6，则结果的日期将会在当前（星期日至星期六）的星期。

如果超出范围，则它将会冒泡到其他星期。

```javascript
moment().day(-7); // 上个星期日 (0 - 7)
moment().day(0); // 这个星期日 (0)
moment().day(7); // 下个星期日 (0 + 7)
moment().day(10); // 下个星期三 (3 + 7)
moment().day(24); // 从现在起第 3 个星期三 (3 + 7 + 7 + 7)
```

注意：`Moment#date` 是月份的日期，而 `Moment#day` 是星期几。

从 **2.1.0** 版开始，还支持星期名称。
这是在 moment 当前的区域设置中解析的。

```javascript
moment().day("Sunday");
moment().day("Monday");
```
