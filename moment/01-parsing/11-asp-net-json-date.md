---
title: moment(JSONDate)
version: 1.3.0
signature: |
  moment(String);
---


默认情况下，Microsoft Web API 会以正确的 ISO-8601 格式返回 JSON 日期，但较早的 ASP.NET 技术可能以 `/Date(1198908717056)/` 或 `/Date(1198908717056-0700)/` 的形式返回 JSON 日期。

如果传入与此格式匹配的字符串，则它将会被正确地解析。

```javascript
moment("/Date(1198908717056-0700)/"); // 2007-12-28T23:11:57.056-07:00
```
