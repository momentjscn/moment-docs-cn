---
title: isSameOrAfter()
version: 2.11.0
signature: |
  moment().isSameOrAfter(Moment|String|Number|Date|Array);
  moment().isSameOrAfter(Moment|String|Number|Date|Array, String);
---

检查一个 moment 是否在另一个 moment 之后或与之相同。
第一个参数会被解析为 moment（如果尚未解析）。

```javascript
moment('2010-10-20').isSameOrAfter('2010-10-19'); // true
moment('2010-10-20').isSameOrAfter('2010-10-20'); // true
moment('2010-10-20').isSameOrAfter('2010-10-21'); // false
```

如果要将粒度限制为毫秒以外的单位，则将单位作为第二个参数传入。

由于第二个参数用于确定精度，且不仅仅是要检查的单个值，因此使用 day 将会检查年份、月份、日期。

```javascript
moment('2010-10-20').isSameOrAfter('2011-12-31', 'year'); // false
moment('2010-10-20').isSameOrAfter('2010-01-01', 'year'); // true
moment('2010-10-20').isSameOrAfter('2009-12-31', 'year'); // true
```

与 `moment#isSame` 和 `moment#isBefore` 一样，`moment#startOf` 支持的任何时间单位也适用于 `moment#isSameOrAfter`：

```
year month week isoWeek day hour minute second
```
