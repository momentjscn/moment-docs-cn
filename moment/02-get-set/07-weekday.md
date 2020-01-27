---
title: weekday()
version: 2.1.0
signature: |
  moment().weekday(Number);
  moment().weekday(); // 数字
---

根据区域设置获取或设置星期几。

如果区域设置将星期一指定为一周的第一天，则 `moment().weekday(0)` 将会是星期一。
如果星期日是一周的第一天，则 `moment().weekday(0)` 将会是星期日。

与 `moment#day` 一样，如果超出范围，则它将会冒泡到其他星期。

```javascript
// 当星期一是一周的第一天时。
moment().weekday(-7); // 上个星期一
moment().weekday(7); // 下个星期一
// 当星期日是一周的第一天时。
moment().weekday(-7); // 上个星期日
moment().weekday(7); // 下个星期日
```
