---
title: toISOString()
version: 2.1.0
signature: |
  moment().toISOString();
  moment().toISOString(keepOffset); // 从 2.20.0 开始
---

将字符串格式化为 ISO8601 标准。

```javascript
moment().toISOString() // 2013-02-04T22:44:30.652Z
```

注意，即使问题中的 moment 处于本地模式，``.toISOString()`` 也会以 UTC 返回时间戳。
这样做是为了与 [ES2015 规范][ecma_sec-date.prototype.toisostring]中概述的原生 JavaScript Date ``.toISOString()`` 规范保持一致。
从 **2.20.0** 版本开始，可以调用 `.toISOString(true)` 以防止 UTC 转换。

从 **2.8.4** 版本开始，出于性能原因，尽可能使用原生 `Date.prototype.toISOString`。

