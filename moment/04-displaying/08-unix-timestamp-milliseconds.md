---
title: valueOf()
version: 1.0.0
signature: |
  moment().valueOf();
  +moment();
---

`moment#valueOf` 简单地输出自 Unix 纪元以来的毫秒数，就像 `Date#valueOf` 一样。

```javascript
moment(1318874398806).valueOf(); // 1318874398806
+moment(1318874398806); // 1318874398806
```

要从 `Moment` 获取 Unix 时间戳（自该纪元以来的秒数），则使用 `moment#unix`。

[注意：ECMAScript 将此称为“时间值”][sec-time-values-and-time-range]。

