---
title: normalizeUnits()
version: 2.3.0
signature: |
  moment.normalizeUnits(String);
---


Moment 的许多函数都允许调用者传入单位枚举的别名。
例如，下面的所有 `get` 都是等效的。

```javascript
var m = moment();
m.get('y');
m.get('year');
m.get('years');
```

如果要扩展库，则可能需要访问 Moment 的工具，以便更好地使函数与 Moment 的函数保持一致。

```javascript
moment.normalizeUnits('y');      // 'year'
moment.normalizeUnits('Y');      // 'year'
moment.normalizeUnits('year');   // 'year'
moment.normalizeUnits('years');  // 'year'
moment.normalizeUnits('YeARS');  // 'year'
```
