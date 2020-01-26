---
title: 解析
---


Moment.js 会为 `Date` 对象创建封装器，而不是修改本地的 `Date.prototype`。
若要获取此封装器对象，则只需使用一种受支持的输入类型调用 `moment()` 即可。

`Moment` 原型通过 `moment.fn` 公开。
如果要添加自己的函数，则可以在其中放置它们。

为了便于参考，`Moment.prototype` 上的任何方法都将会在文档中称为 `moment＃method`。
因此 `Moment.prototype.format` == `moment.fn.format` == `moment＃format`。

**请阅读：**
* `moment(...)` 是本地模式。不明确的输入（无偏移量）会被假定为本地时间。明确的输入（带偏移量）会被调整为本地时间。
* `moment.utc(...)` 是 utc 模式。不明确的输入会被假定为 UTC。明确的输入会被调整为 UTC。
* `moment.parseZone()` 会保持输入的区域被传入。如果输入不明确，则与本地模式相同。
* `moment.tz(...)` 使用 moment-timezone 插件可以以特定的时区来解析输入。

记住，时区和时区偏移是两件事。 
-08:00 的偏移量不一定意味着你处于美国太平洋时区。

[有关其他信息，参见解析指南][guides_parsing]。

