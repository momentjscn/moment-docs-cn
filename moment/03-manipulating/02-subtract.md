---
title: subtract()
version: 1.0.0
signature: |
  moment().subtract(Number, String);
  moment().subtract(Duration);
  moment().subtract(Object);
---

通过减去时间来改变原始的 moment。

这与 `moment#add` 完全相同，只是不增加时间，而是减去时间。

```javascript
moment().subtract(7, 'days');
```

在 **2.8.0** 版本之前，还支持 `moment#subtract(String, Number)` 语法。
不推荐使用它，而使用 `moment#subtract(Number, String)`。

```javascript
moment().subtract('seconds', 1); // 废弃于 2.8.0
moment().subtract(1, 'seconds');
```

从 **2.12.0** 版本开始，当为日期和月份传入小数时，它们会被四舍五入到最接近的整数。
星期、季度、年份会被转换到日期或月份，然后四舍五入到最接近的整数。

```javascript
moment().subtract(1.5, 'months') == moment().subtract(2, 'months')
moment().subtract(.7, 'years') == moment().subtract(8, 'months') //.7*12 = 8.4，取整到 8
```

注意，为了使操作 ``moment.add(-.5, 'days')`` 和 ``moment.subtract(.5, 'days')`` 等价，-。5、-1.5、-2.5 等都向下舍入。

