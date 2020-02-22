---
title: toJSON()
version: 2.9.0
signature: |
  moment.duration().toJSON();
---

当将时长对象序列化为 JSON 时，它将会表示为 ISO8601 字符串。

```javascript
JSON.stringify({
    postDuration : moment.duration(5, 'm')
}); // '{"postDuration":"PT5M"}'
```

无效的时长返回 json 表示的 `Invalid Date`。

