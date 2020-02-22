---
title: humanize()
version: 1.6.0
signature: |
  moment.duration().humanize();
---

有时，只想要 `moment#from` 的所有优点，但又不想创建两个 moment，而只想显示一段时长。

使用 `moment.duration().humanize()`。

```javascript
moment.duration(1, "minutes").humanize(); // 1 分钟
moment.duration(2, "minutes").humanize(); // 2 分钟
moment.duration(24, "hours").humanize();  // 1 天
```

默认情况下，返回的字符串是没有后缀。 
如果需要后缀，则按如下所示传入 true。

```javascript
moment.duration(1, "minutes").humanize(true); // 1 分钟内
```

对于当前时间之前的后缀，则传入负数。

```javascript
moment.duration(-1, "minutes").humanize(true); // 1 分钟前
```

无效的时长会被人性化为 `Invalid Date` 的本地化版本。

```javascript
moment.duration.invalid().humanize(); // Invalid Date
```
