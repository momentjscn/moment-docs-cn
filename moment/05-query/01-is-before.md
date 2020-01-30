---
title: isBefore()
version: 2.0.0
signature: |
  moment().isBefore(Moment|String|Number|Date|Array);
  moment().isBefore(Moment|String|Number|Date|Array, String);
---

检查一个 moment 是否在另一个 moment 之前。
第一个参数会被解析为 moment（如果尚未解析）。

```javascript
moment('2010-10-20').isBefore('2010-10-21'); // true
```

如果要将粒度限制为毫秒以外的单位，则将单位作为第二个参数传入。

由于第二个参数用于确定精度，且不仅仅是要检查的单个值，因此使用 day 将会检查年份、月份、日期。

```javascript
moment('2010-10-20').isBefore('2010-12-31', 'year'); // false
moment('2010-10-20').isBefore('2011-01-01', 'year'); // true
```

与 `moment#isAfter` 和 `moment#isSame` 一样，`moment#startOf` 支持的任何时间单位也适用于 `moment#isBefore`。

```
year month week isoWeek day hour minute second
```

如果未将任何内容传给 `moment#isBefore`，则它将会默认为当前时间。

注意：`moment().isBefore()` 具有未定义的行为，且不应被使用！
如果代码运行快速，则初始创建的 moment 将会与isBefore 中创建的要执行检查的相同，因此结果将会为 `false`。
但是，如果代码运行速度较慢，则有可能在 isBefore 中创建的 moment 可测量地在 `moment()` 中创建的之后，因此该调用将会返回 `true`。

