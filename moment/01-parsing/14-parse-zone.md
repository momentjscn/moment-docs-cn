---
title: parseZone()
version: 2.3.0
signature: |
  moment.parseZone()
  moment.parseZone(String)
  moment.parseZone(String, String)
  moment.parseZone(String, [String])
  moment.parseZone(String, String, Boolean)
  moment.parseZone(String, String, String, Boolean)
---

Moment 的字符串解析函数（例如 `moment(string)` 和 `moment.utc(string)`）接受偏移量的信息（如果提供），但会将生成的 Moment 对象转换为本地或 UTC 时间。
相比之下，`moment.parseZone()` 解析字符串，但会将生成的 Moment 对象保持在固定偏移量的时区中（使用字符串中提供的偏移量）。

```javascript
moment.parseZone("2013-01-01T00:00:00-13:00").utcOffset(); // -780 (总分钟数 "-13:00")
moment.parseZone('2013 01 01 05 -13:00', 'YYYY MM DD HH ZZ').utcOffset(); // -780  (总分钟数 "-13:00")
moment.parseZone('2013-01-01-13:00', ['DD MM YYYY ZZ', 'YYYY MM DD ZZ']).utcOffset(); // -780  (总分钟数 "-13:00");
```

它还允许传入区域设置和严格性参数。

```javascript
moment.parseZone("2013 01 01 -13:00", 'YYYY MM DD ZZ', true).utcOffset(); // -780  (总分钟数 "-13:00")
moment.parseZone("2013-01-01-13:00", 'YYYY MM DD ZZ', true).utcOffset(); // NaN (未通过严格性检查)
moment.parseZone("2013 01 01 -13:00", 'YYYY MM DD ZZ', 'fr', true).utcOffset(); // -780 (带有区域设置和严格性参数)
moment.parseZone("2013 01 01 -13:00", ['DD MM YYYY ZZ', 'YYYY MM DD ZZ'], 'fr', true).utcOffset(); // -780 (带有区域设置和严格性参数以及格式的数组)
```

`moment.parseZone` 等效于解析字符串并使用 `moment#utcOffset` 解析区域。

```javascript
var s = "2013-01-01T00:00:00-13:00";
moment(s).utcOffset(s);
```
