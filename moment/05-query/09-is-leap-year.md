---
title: isLeapYear()
version: 1.0.0
signature: |
  moment().isLeapYear();
---

如果该年是闰年，则 `moment#isLeapYear` 返回 `true`，否则返回 `false`。

```javascript
moment([2000]).isLeapYear() // true
moment([2001]).isLeapYear() // false
moment([2100]).isLeapYear() // false
```
