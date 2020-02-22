---
title: locale()
version: 2.17.1
signature: |
  moment.duration().locale();
  moment.duration().locale(String);
---

可以使用 `locale(...)` 获取或设置时长的语言环境。
语言环境将会影响时长的字符串方法，例如 `humanize()`。
有关国际化的常用信息，请参见[国际化][i18n]章节。

```javascript
moment.duration(1, "minutes").locale("en").humanize(); // a minute
moment.duration(1, "minutes").locale("fr").humanize(); // une minute
moment.duration(1, "minutes").locale("es").humanize(); // un minuto
```

`humanize()` 的后缀也已国际化：

```javascript
moment.duration(1, "minutes").locale("en").humanize(true); // in a minute
moment.duration(1, "minutes").locale("fr").humanize(true); // dans une minute
moment.duration(1, "minutes").locale("es").humanize(true); // en un minuto

moment.duration(-1, "minutes").locale("en").humanize(true); // a minute ago
moment.duration(-1, "minutes").locale("fr").humanize(true); // il y a une minute
moment.duration(-1, "minutes").locale("es").humanize(true); // hace un minuto
```
