---
title: isoWeekday()
version: 2.1.0
signature: |
  moment().isoWeekday(Number);
  moment().isoWeekday(); // 数字
---


获取或设置 [ISO 星期几][ISO_week_date]，其中 `1` 是星期一、`7` 是星期日。

与 `moment#day` 一样，如果超出范围，则它将会冒泡到其他星期。

```javascript
moment().isoWeekday(1); // 星期一
moment().isoWeekday(7); // 星期日
```

还支持星期名称。 
这是在 moment 当前的语言环境中解析的。

```javascript
moment().isoWeekday("Sunday");
moment().isoWeekday("Monday");
```
