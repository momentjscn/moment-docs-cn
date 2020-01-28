---
title: endOf()
version: 1.7.0
signature: |
  moment().endOf(String);
---

通过将原始的 moment 设置为时间单位的末尾来对其进行更改。

这与 `moment#startOf` 相同，只是将其设置为时间单位的末尾，而不是设置为时间单位的开头。

```javascript
moment().endOf("year"); // 将 moment 设置为今年的 12 月 31 日 23:59:59.999
```

从 **2.0.0** 版本开始，`moment#endOf('day')` 替代 `moment#eod`。

注意：`moment#endOf('week')` 新增于 **2.0.0** 版本。

从 **2.1.0** 版本开始，`moment#endOf('week')` 使用区域设置敏感的星期开始日期。
