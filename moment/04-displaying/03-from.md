---
title: from()
version: 1.0.0
signature: |
  moment().from(Moment|String|Number|Date|Array);
  moment().from(Moment|String|Number|Date|Array, Boolean);
---


可能想要显示 moment 与现在以外的时间的相对时间。
在这种情况下，可以使用 `moment#from`。

```javascript
var a = moment([2007, 0, 28]);
var b = moment([2007, 0, 29]);
a.from(b) // "1 天前"
```

第一个参数是可以传给 `moment()` 的任何值或实际的 `Moment`。

```javascript
var a = moment([2007, 0, 28]);
var b = moment([2007, 0, 29]);
a.from(b);                     // "1 天前"
a.from([2007, 0, 29]);         // "1 天前"
a.from(new Date(2007, 0, 29)); // "1 天前"
a.from("2007-01-29");          // "1 天前"
```

与 `moment#fromNow` 一样，将 `true` 用作第二个参数会返回不带后缀的值。
无论何时需要有可读的时间长度，这都非常有用。

```javascript
var start = moment([2007, 0, 5]);
var end   = moment([2007, 0, 10]);
end.from(start);       // "5 天内"
end.from(start, true); // "5 天"
```

从 **2.10.3** 版本开始，如果任一端点无效，则结果为本地化的无效日期字符串。

