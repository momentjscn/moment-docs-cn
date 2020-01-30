---
title: unix()
version: 1.6.0
signature: |
  moment().unix();
---


`moment#unix` 输出 Unix 时间戳（自 Unix 纪元以来的秒数）

```javascript
moment(1318874398806).unix(); // 1318874398
```

此值的下限为最接近的秒数，且不包括毫秒部分。

