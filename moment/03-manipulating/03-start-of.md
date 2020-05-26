---
title: startOf()
version: 1.7.0
signature: |
  moment().startOf(String);
---

通过将原始的 moment 设置为时间单位的开头来对其进行更改。

```javascript
moment().startOf('year');    // 设置为今年一月1日上午 00:00
moment().startOf('month');   // 设置为本月1日上午 00:00
moment().startOf('quarter');  // 设置为当前季度的开始，即每月的第一天上午 00:00
moment().startOf('week');    // 设置为本周的第一天上午 00:00
moment().startOf('isoWeek'); // 根据 ISO 8601 设置为本周的第一天上午 00:00
moment().startOf('day');     // 设置为今天上午 00:00
moment().startOf('date');     // 设置为今天上午 00:00
moment().startOf('hour');    // 设置为当前时间，但是 0 分钟、0 秒钟、0 毫秒
moment().startOf('minute');  // 设置为当前时间，但是 0 秒钟、0 毫秒
moment().startOf('second');  // 与 moment().milliseconds(0); 相同
```

这些快捷方式与以下的基本相同。

```javascript
moment().startOf('year');
moment().month(0).date(1).hours(0).minutes(0).seconds(0).milliseconds(0);
```

```javascript
moment().startOf('hour');
moment().minutes(0).seconds(0).milliseconds(0)
```

从 **2.0.0** 版本开始，`moment#startOf('day')` 替代 `moment#sod`。

注意：`moment#startOf('week')` 新增于 **2.0.0** 版本。

从 **2.1.0** 版本开始，`moment#startOf('week')` 使用语言环境敏感的星期开始日期。

注意：`moment#startOf('isoWeek')` 新增于 **2.2.0** 版本。

注意：`moment#startOf('date')` 作为 day 的别名新增于 **2.13.0**。
