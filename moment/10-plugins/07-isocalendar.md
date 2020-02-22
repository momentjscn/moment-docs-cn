---
title: isocalendar
signature: |
  npm install moment-isocalendar
---


如果你正在寻找类似 Python 的 isocalendar 方法，则可以使用 Rocky Meza 的插件

`moment-isocalendar`

在 moment 上调用 isocalendar 方法将会返回如下数组：

`[year, week_of_year, day_of_week, minutes_since_midnight]`


```javascript
moment().isocalendar(); // [2012, 8, 5, 870]
```

还可以从 isocalendar 数组重造 moment。

```javascript
moment.fromIsocalendar([2011, 51, 5, 870]).format('LLLL');
// "Friday, December 23 2011 2:30 PM"
```

该仓库位于 [github.com/fusionbox/moment-isocalendar][moment-isocalendar]。
