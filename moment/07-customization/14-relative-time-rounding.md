---
title: relativeTimeRounding()
version: 2.14.0
signature: |
  moment.relativeTimeRounding();  // getter
  moment.relativeTimeRounding(fn);  // setter
---

`duration.humanize` 在将其提供给语言环境中指定的 relativeTime 格式字符串之前，会舍入一个可能为双精度的值。
要控制舍入，则可以使用 `moment.relativeTimeRounding`。

```javascript
var roundingDefault = moment.relativeTimeRounding();

// 向下舍入相对时间。
moment.relativeTimeRounding(Math.floor);

moment.relativeTimeThreshold('s', 60);
moment.relativeTimeThreshold('m', 60);
moment.relativeTimeThreshold('h', 24);
moment.relativeTimeThreshold('d', 31);
moment.relativeTimeThreshold('M', 12);

var a = moment();
a.subtract({hours: 23, minutes: 59, seconds: 59});
a.toNow()  // == '23 小时内'  '向下舍入到最近的小时'

// 回退到默认值。
moment.relativeTimeRounding(roundingDefault);
```

甚至可以选择完全不舍入：

```javascript
var retainValue = function (value) {
    return value;
};
moment.relativeTimeRounding(retainValue);

var a = moment();
a.subtract({hours: 39});
a.toNow() // == '1.625 天内', '向下舍入到最近的年份'
```
