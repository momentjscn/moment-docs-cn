---
title: now
version: 2.11.0
signature: |
  moment.now = function () { return +new Date(); }
---

如果要更改 Moment 看到的时间，可以指定一个方法，该方法返回自 Unix 纪元（1970年1月1日）以来的毫秒数。

默认为：

```javascript
moment.now = function () {
    return +new Date();
}
```

这将会在调用 `moment()` 时使用，而在 `format()` 中省略令牌时使用的当前日期。 
通常，任何需要当前时间的方法都可以在后台使用。

