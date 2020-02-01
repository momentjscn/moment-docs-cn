---
title: months()/weekdays()
version: 2.3.0
signature: |
  moment.months()
  moment.monthsShort()
  moment.weekdays()
  moment.weekdaysShort()
  moment.weekdaysMin()
---

有时需要在语言环境中获取月份或工作日的列表，例如当填充下拉菜单时。

```javascript
moment.months();
```

返回当前语言环境中的月份列表。

```javascript
[ 'January',
  'February',
  'March',
  'April',
  'May',
  'June',
  'July',
  'August',
  'September',
  'October',
  'November',
  'December' ]
```

同样，`moment.monthsShort` 返回缩写的月份名称，`moment.weekdays`、`moment.weekdaysShort`、`moment.weekdaysMin` 返回工作日的列表。

可以将整数传给每个函数以获取特定的月份或工作日。

```javascript
moment.weekdays(3); // 'Wednesday'
```

从 **2.13.0** 开始，可以将布尔值作为 weekday 函数的第一个参数传入。
如果为 `true`，则将会按特定于语言环境的顺序返回工作日。
例如，在阿拉伯语言环境中，星期六是一周的第一天，因此：

```javascript
moment.locale('ar');
moment.weekdays(true); // 以阿拉伯语列出周六至周五的工作日列表
moment.weekdays(true, 2); // 将会以阿拉伯语返回星期一
```

注意：如果缺少语言环境特定的参数，则无论星期几是本地的第一天，工作日始终将星期日作为索引 0。

当格式化月份名称时，某些语言环境会特别考虑。
例如，荷兰语格式化月份的缩写时不带末尾的句号，但前提是格式化破折号之间的月份。 
`months` 方法支持传入格式，以便在适当的上下文中列出月份。

```javascript
moment.locale('nl');
moment.monthsShort(); // ['jan.', 'feb.', 'mrt.', ...]
moment.monthsShort('-MMM-'); // [ 'jan', 'feb', 'mrt', ...]
```

最后，可以结合使用格式选项和整数选项。

```javascript
moment.monthsShort('-MMM-', 3); // 'apr'
```
