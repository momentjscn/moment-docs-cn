---
title: isBetween()
version: 2.9.0
signature: |
  //从 2.13.0 开始
  moment().isBetween(moment-like, moment-like);
  moment().isBetween(moment-like, moment-like, String);
  moment().isBetween(moment-like, moment-like, String, String);
  // 其中 moment-like 是 Moment|String|Number|Date|Array

  //2.9.0 至 2.12.0
  moment().isBetween(moment-like, moment-like);
  moment().isBetween(moment-like, moment-like, String);
  // 其中 moment-like 是 is Moment|String|Number|Date|Array
---

检查一个 moment 是否在其他两个 moment 之间，可选地检查指定的单位刻度（分钟，小时，日期等）。
这个匹配是排他的。
前两个参数会被解析为 moment（如果尚未解析）。

```javascript
moment('2010-10-20').isBetween('2010-10-19', '2010-10-25'); // true
moment('2010-10-20').isBetween('2010-10-19', undefined); // true, 因为 moment(undefined) 等效于 moment()
```

如果要将粒度限制为毫秒以外的单位，则将单位作为第三个参数传入。

```javascript
moment('2010-10-20').isBetween('2010-01-01', '2012-01-01', 'year'); // false
moment('2010-10-20').isBetween('2009-12-31', '2012-01-01', 'year'); // true
```

与 `moment#isSame`、`moment#isBefore`、`moment#isAfter` 一样，`moment#startOf` 支持的任何时间单位也适用于 `moment#isBetween`。
年份、月份、星期、ISO星期、日期、小时、分钟、秒钟。

**2.13.0** 版本引入了包容性。
``[`` 表示包含。 
``(`` 表示排除。
如果使用包容性参数，则必须传入两个指示符。

```javascript
moment('2016-10-30').isBetween('2016-10-30', '2016-12-30', null, '()'); //false
moment('2016-10-30').isBetween('2016-10-30', '2016-12-30', null, '[)'); //true
moment('2016-10-30').isBetween('2016-01-01', '2016-10-30', null, '()'); //false
moment('2016-10-30').isBetween('2016-01-01', '2016-10-30', null, '(]'); //true
moment('2016-10-30').isBetween('2016-10-30', '2016-10-30', null, '[]'); //true
```

注意，如果 ``from`` 和 ``to`` 参数相同，但包容性参数不同，则将会返回 false。

```javascript
moment('2016-10-30').isBetween('2016-10-30', '2016-10-30', null, '(]'); //false
```

如果未指定包容性参数，则 Moment 将会默认为 ``()``。

