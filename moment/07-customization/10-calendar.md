---
title: calendar
version: 1.3.0
signature: |
  // 从 2.12.0 开始
  moment.updateLocale('en', {
      calendar : Object
  });
  // 从 2.8.1 至 2.11.2
  moment.locale('en', {
      calendar : Object
  });

  // 废弃于 2.8.1
  moment.lang('en', {
      calendar : Object
  });
---


`Locale#calendar` 应是具有以下格式的字符串。

```javascript
moment.locale('en', {
    calendar : {
        lastDay : '[Yesterday at] LT',
        sameDay : '[Today at] LT',
        nextDay : '[Tomorrow at] LT',
        lastWeek : '[last] dddd [at] LT',
        nextWeek : 'dddd [at] LT',
        sameElse : 'L'
    }
});
```

每个 `Locale#calendar` 键也可以是一个回调函数，具有当前 moment 的范围，且第一个参数是描述现在的 moment。
它应该返回一个格式化字符串。

```javascript
function callback (now) {
    return '[hoy a la' + ((this.hours() !== 1) ? 's' : '') + '] LT';
}
```
