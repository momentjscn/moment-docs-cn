---
title: invalidDate
version: 2.3.0
signature: |
  // 从 2.12.0 开始
  moment.updateLocale('en', {
      invalidDate : String
  });

  // 从 2.8.1 至 2.11.2
  moment.locale('en', {
      invalidDate : String
  });

  // 废弃于 2.8.1
  moment.lang('en', {
      invalidDate : String
  });
---

`Locale#invalidDate` 应是一个字符串。

```javascript
moment.updateLocale("en", {
  invalidDate: "Fecha invalida"
});
```
