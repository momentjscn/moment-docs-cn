---
title: weekdaysShort
version: 1.0.0
signature: |
  // 从 2.12.0 开始
  moment.updateLocale('en', {
      weekdaysShort : String[]
  });
  moment.updateLocale('en', {
      weekdaysShort : Function
  });
  // 从 2.8.1 至 2.11.2
  moment.locale('en', {
      weekdaysShort : String[]
  });
  moment.locale('en', {
      weekdaysShort : Function
  });

  // 废弃于 2.8.1
  moment.lang('en', {
      weekdaysShort : String[]
  });
  moment.lang('en', {
      weekdaysShort : Function
  });
---


`Locale#weekdaysShort` 应是工作日缩写的数组。

```javascript
moment.updateLocale('en', {
    weekdaysShort : ["Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"]
});
```

`Locale#weekdaysShort` 也可以是回调函数。

```javascript
moment.updateLocale('en', {
    weekdaysShort : function (momentToFormat, format) {
        return weekdaysShort[momentToFormat.day()];
    }
});
```
