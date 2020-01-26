---
title: unix()
version: 1.6.0
signature: |
  moment.unix(Number)
---


若要从 Unix 时间戳（自 Unix 纪元以来的秒数）创建 moment，则使用 `moment.unix(Number)`。

```javascript
var day = moment.unix(1318781876);
```

这实现为 `moment(timestamp * 1000)`，因此在输入时间戳中包含了部分秒数。

```javascript
var day = moment.unix(1318781876.721);
```

注意：尽管 Unix 时间戳是基于 UTC 的，但是此函数在本地模式中创建了 moment 对象。 
如果需要 UTC，则可以随后调用 `.utc()`，如下所示：

```javascript
var day = moment.unix(1318781876).utc();
```
