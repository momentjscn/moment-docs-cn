---
title: weekdaysMin
version: 1.7.0
signature: |
  // 从 2.12.0 开始
  moment.updateLocale('en', {
      weekdaysMin : String[]
  });
  moment.updateLocale('en', {
      weekdaysMin : Function
  });

  // 从 2.8.1 至 2.11.2
  moment.locale('en', {
      weekdaysMin : String[]
  });
  moment.locale('en', {
      weekdaysMin : Function
  });

  // 废弃于 2.8.1
  moment.lang('en', {
      weekdaysMin : String[]
  });
  moment.lang('en', {
      weekdaysMin : Function
  });
---


`Locale#weekdaysMin` 应是两个字母的工作日缩写的数组。
它们的目的是用于日历选择器之类的，因此它们应尽可能短小。

```javascript
moment.updateLocale('en', {
    weekdaysMin : ["Su", "Mo", "Tu", "We", "Th", "Fr", "Sa"]
});
```

`Locale#weekdaysMin` 也可以是回调函数。

```javascript
moment.updateLocale('en', {
    weekdaysMin : function (momentToFormat, format) {
        return weekdaysMin[momentToFormat.day()];
    }
});
```
