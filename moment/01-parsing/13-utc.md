---
title: utc()
version: 1.5.0
signature: |
  moment.utc();
  moment.utc(Number);
  moment.utc(Number[]);
  moment.utc(String);
  moment.utc(String, String);
  moment.utc(String, String[]);
  moment.utc(String, String, String);
  moment.utc(String, String, Boolean);
  moment.utc(String, String, String, Boolean);
  moment.utc(Moment);
  moment.utc(Date);
---

默认情况下，moment 会解析并以本地时间显示。

如果要解析或以 UTC 显示 moment，则可以使用 `moment.utc()` 而不是 `moment()`。

这为我们带来了 Moment.js 的有趣的特性。 
UTC 模式。

在 UTC 模式中，所有的显示方法都将会以 UTC 时间（而非本地时间）显示。

```javascript
moment().format();     // 2013-02-04T10:35:24-08:00
moment.utc().format(); // 2013-02-04T18:35:24+00:00
```

此外，在 UTC 模式中，所有的 getter 和 setter 都将会在内部使用 `Date#getUTC*` 和 `Date#setUTC*` 方法，而不是 `Date#get*` 和 `Date#set*` 方法。

```javascript
moment.utc().seconds(30).valueOf() === new Date().setUTCSeconds(30);
moment.utc().seconds()   === new Date().getUTCSeconds();
```

重要的是要注意，尽管上面的显示有所不同，但它们在同一时间都是相同的 moment。

```javascript
var a = moment();
var b = moment.utc();
a.format();  // 2013-02-04T10:35:24-08:00
b.format();  // 2013-02-04T18:35:24+00:00
a.valueOf(); // 1360002924000
b.valueOf(); // 1360002924000
```

使用 `moment.utc()` 创建的任何 moment 都将会处于 UTC 模式中，而使用 `moment()` 创建的任何 moment 则不会。

若要从 UTC 切换到本地时间，则可以使用 [moment#utc][manipulating_utc] 或 [moment#local][manipulating_local]。

```javascript
var a = moment.utc([2011, 0, 1, 8]);
a.hours(); // 8 UTC
a.local();
a.hours(); // 0 PST
```
