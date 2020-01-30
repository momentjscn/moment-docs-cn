---
title: diff()
version: 1.0.0
signature: |
  moment().diff(Moment|String|Number|Date|Array);
  moment().diff(Moment|String|Number|Date|Array, String);
  moment().diff(Moment|String|Number|Date|Array, String, Boolean);
---

要获取以毫秒为单位的差异，则像使用 `moment#from` 一样使用 `moment#diff`。

```javascript
var a = moment([2007, 0, 29]);
var b = moment([2007, 0, 28]);
a.diff(b) // 86400000
```

要获取另一个度量单位中的差异，则将该度量作为第二个参数传入。

```javascript
var a = moment([2007, 0, 29]);
var b = moment([2007, 0, 28]);
a.diff(b, 'days') // 1
```

要获取两个时刻之间的差值的时长，则可以将 `diff` 作为参数传给 `moment#duration`。
有关更多信息，参阅 [moment#duration][moment.duration] 上的文档。

支持的度量有 `years`、`months`、`weeks`、`days`、`hours`、`minutes` 和 `seconds`。
为了便于开发，从 **2.0.0** 版本开始支持单数形式。
**1.1.1** 版本中提供了毫秒以外的度量单位。

默认情况下，`moment#diff` 会将结果截断为零个小数位，并返回一个整数。
如果需要浮点数，则将 `true` 作为第三个参数传入。
在 **2.0.0** 之前，`moment#diff` 返回的数字会四舍五入到最接近的整数，而不是截断的数字。

```javascript
var a = moment([2008, 9]);
var b = moment([2007, 0]);
a.diff(b, 'years');       // 1
a.diff(b, 'years', true); // 1.75
```

如果该时刻早于传给 `moment.fn.diff` 的时刻，则返回值为负数。

```javascript
var a = moment();
var b = moment().add(1, 'seconds');
a.diff(b) // -1000
b.diff(a) // 1000
```

考虑这一点的一种简单方法是将 `.diff(` 替换为减号运算符。

```javascript
          // a < b
a.diff(b) // a - b < 0
b.diff(a) // b - a > 0
```

#### 月份和年份的差异

`moment#diff` 对月份和年份的差异进行一些特殊处理。
它做了一些优化，以确保具有相同日期的两个月始终是整数。

因此，1月15日至2月15日应该恰好是1个月。

2月28日至3月28日应该恰好是1个月。

2011年2月28日至2012年2月28日应该恰好是1年。

[在此处查看有关月份和年份的差异的更多讨论][moment_pull_571]。

对月份和年份的差异的更改于 **2.0.0**。
从 **2.9.0** 版本开始，diff 还支持季度单位。

