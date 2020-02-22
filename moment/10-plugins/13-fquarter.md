---
title: fquarter
---


如果需要[财政][Fiscal_year]、日历或学术季度，可以使用 [@robgallen][robgallen] 的 [moment-fquarter][moment-fquarter] 插件。

最简单的是，只需在任何 moment 对象上调用 fquarter 方法。
它返回格式化的字符串，其中四月是第一季度。

```javascript
moment("2013-01-01").fquarter();
// Q4 2012/13
```

可以将任何月份作为起始季度，例如七月：

```javascript
moment("2013-01-01").fquarter(7);
// Q3 2012/13
```

如果需要日历季度，则从一月开始：

```javascript
moment("2013-01-01").fquarter(1);
// Q1 2013
```
