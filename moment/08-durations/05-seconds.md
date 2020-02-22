---
title: seconds()
version: 1.6.0
signature: |
  moment.duration().seconds();
  moment.duration().asSeconds();
---


要获取时长的秒数，则使用 `moment.duration().seconds()`。

它将会返回 0 至 59 之间的数字。

```javascript
moment.duration(500).seconds(); // 0
moment.duration(1500).seconds(); // 1
moment.duration(15000).seconds(); // 15
```

如果想要时长的长度（以秒为单位），则改用 `moment.duration().asSeconds()`。

```javascript
moment.duration(500).asSeconds(); // 0.5
moment.duration(1500).asSeconds(); // 1.5
moment.duration(15000).asSeconds(); // 15
```
