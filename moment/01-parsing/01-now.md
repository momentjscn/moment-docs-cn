---
title: moment()
version: 1.0.0
signature: |
  moment();
  moment(undefined);
  // 从 2.14.0 开始，也受支持。
  moment([]);
  moment({});
---


要获取当前的日期和时间，只需调用不带参数的 `moment()` 即可。

```javascript
var now = moment();
```

这基本上与调用 `moment(new Date())` 相同。

从 **2.14.0** 版本开始，`moment([])` 和 `moment({})` 也返回当前时间。 
在 **2.14.0** 之前，它们默认为今天开始，但这是随意的，因此已更改。

函数参数在未传入时默认为 `undefined`。
Moment 会将 `moment(undefined)` 视作 `moment()`。

```javascript
var x = undefined;
moment(x).isSame(moment(), 'second'); // true
```
