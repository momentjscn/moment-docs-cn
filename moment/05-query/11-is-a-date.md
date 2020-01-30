---
title: isDate()
version: 2.9.0
signature: |
  moment.isDate(obj);
---

要检查变量是否为原生 js Date 对象，则使用 `moment.isDate()`。

```javascript
moment.isDate(); // false
moment.isDate(new Date()); // true
moment.isDate(moment()); // false
```
