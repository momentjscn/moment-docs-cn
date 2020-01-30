---
title: isSame()
version: 2.0.0
signature: |
  moment().isSame(Moment|String|Number|Date|Array);
  moment().isSame(Moment|String|Number|Date|Array, String);
---

检查一个 moment 是否与另一个 moment 相同。
第一个参数会被解析为 moment（如果尚未解析）。

```javascript
moment('2010-10-20').isSame('2010-10-20'); // true
```

如果要将粒度限制为毫秒以外的单位，则将单位作为第二个参数传入。

```javascript
moment('2010-10-20').isSame('2009-12-31', 'year');  // false
moment('2010-10-20').isSame('2010-01-01', 'year');  // true
moment('2010-10-20').isSame('2010-12-31', 'year');  // true
moment('2010-10-20').isSame('2011-01-01', 'year');  // false
```

当包含第二个参数时，则它将会匹配所有等于或更大的单位。
传入 `month` 将会检查 `month` 和 `year`。
传入 `day` 将会检查 `day`、`month` 和 `year`。

```javascript
moment('2010-01-01').isSame('2011-01-01', 'month'); // false, 不同的年份
moment('2010-01-01').isSame('2010-02-01', 'day');   // false, 不同的月份
```

与 `moment#isAfter` 和 `moment#isBefore` 一样，`moment#startOf` 支持的任何时间单位也适用于 `moment#isSame`。

```
year month week isoWeek day hour minute second
```

如果两个 moment 的时区不同，则第一 moment 的时区会被用于比较。

```javascript
// 注意：澳大利亚/悉尼在这些日期的 UTC+11:00
moment.tz("2018-11-09T10:00:00", "Australia/Sydney").isSame(moment.tz("2018-11-08T12:00:00", "UTC"), "day"); // false
moment.tz("2018-11-08T12:00:00", "UTC").isSame(moment.tz("2018-11-09T10:00:00", "Australia/Sydney"), "day"); // true
```

注意：`moment().isSame()` 具有未定义的行为，且不应被使用！
如果代码运行快速，则初始创建的 moment 将会与isSame 中创建的要执行检查的相同，因此结果将会为 `true`。
但是，如果代码运行速度较慢，则有可能在 isSame 中创建的 moment 可测量地在 `moment()` 中创建的之后，因此该调用将会返回 `false`。

