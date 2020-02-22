---
title: milliseconds()
version: 1.6.0
signature: |
  moment.duration().milliseconds();
  moment.duration().asMilliseconds();
---


要获取时长的毫秒数，则使用 `moment.duration().milliseconds()`。

它将会返回 0 至 999 之间的数字。

```javascript
moment.duration(500).milliseconds(); // 500
moment.duration(1500).milliseconds(); // 500
moment.duration(15000).milliseconds(); // 0
```

如果想要时长的长度（以毫秒为单位），则改用 `moment.duration().asMilliseconds()`。

```javascript
moment.duration(500).asMilliseconds(); // 500
moment.duration(1500).asMilliseconds(); // 1500
moment.duration(15000).asMilliseconds(); // 15000
```
