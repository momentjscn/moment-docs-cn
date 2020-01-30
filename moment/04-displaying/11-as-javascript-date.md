---
title: toDate()
version: 1.0.0
signature: |
  moment().toDate();
---

要获取 Moment.js 封装的原生 Date 对象的副本，则使用 `moment#toDate`。

这将会返回该 moment 使用的 `Date` 的副本，因此对该 `Date` 的任何更改都不会导致 moment 发生变化。 
如果要更改 moment 的 `Date`，则参阅 `moment#manipulate` 或 `moment#set`。

`moment#native` 已由 `moment#toDate` 取代，并已弃用于 **1.6.0**。

