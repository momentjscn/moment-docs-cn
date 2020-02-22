---
title: jdateformatparser
signature: |
  npm install moment-jdateformatparser
---

如果要使用 `java.text.DateFormat`，可以使用此插件。

例如，

```javascript
moment("2013-12-24 14:30").formatWithJDF("dd.MM.yyyy");  // 返回格式化的日期 "24.12.2013"
moment().toJDFString("DD.MM.YYYY");  // 返回 Java 的格式模式 "dd.MM.yyyy"
```

该仓库位于 [github.com/MadMG/moment-jdateformatparser][moment-jdateformatparser]。
