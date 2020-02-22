---
title: get()
version: 2.1.0
signature: |
  moment.duration().get(String);
---


作为 `Duration#x()` 获取器的替代，可以使用 `Duration#get('x')`。 
同样，`moment#add` 中的所有[简写键][moment.add]也适用于此。

```javascript
duration.get('hours');
duration.get('minutes');
duration.get('seconds');
duration.get('milliseconds');
```

无效的时长将会为所有单位返回 `NaN`。

