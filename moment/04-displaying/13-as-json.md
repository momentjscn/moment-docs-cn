---
title: toJSON()
version: 2.0.0
signature: |
  moment().toJSON();
---

当将对象序列化为 JSON 时，如果有 `Moment` 对象，则它会将被解释为 ISO8601 字符串，并调整到 UTC。

```javascript
JSON.stringify({
    postDate : moment()
}); // '{"postDate":"2013-02-04T22:44:30.652Z"}'
```

如果希望使用一个 ISO8601 字符串来反映该 moment 的 `utcOffset()`，则可以像这样修改 `toJSON` 函数：

```javascript
moment.fn.toJSON = function() { return this.format(); }
```

这会更改行为，如下所示：

```javascript
JSON.stringify({
    postDate : moment()
}); // '{"postDate":"2013-02-04T14:44:30-08:00"}'
```
