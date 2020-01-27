---
title: creationData()
version: 2.11.0
signature: |
  moment().creationData();
---

创建 moment 对象之后，可以使用 `creationData()` 方法访问所有的输入：

<!-- skip-example -->

```javascript
moment("2013-01-02", "YYYY-MM-DD", true).creationData() === {
    input: "2013-01-02",
    format: "YYYY-MM-DD",
    locale: 区域设置对象,
    isUTC: false,
    strict: true
}
```
