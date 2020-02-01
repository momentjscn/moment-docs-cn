---
title: longDateFormat
version: 1.1.0
signature: |
  // 从 2.12.0 开始
  moment.updateLocale('en', {
      longDateFormat : Object
  });

  // 从 2.8.1 至 2.11.2
  moment.locale('en', {
      longDateFormat : Object
  });

  // 废弃于 2.8.1
  moment.lang('en', {
      longDateFormat : Object
  });
---


`Locale#longDateFormat` 应是一个包含每个长日期格式 `L LL LLL LLLL LT LTS` 的键/值对的对象。 
`LT` 应是时间格式，也用于 `moment#calendar`。

```javascript
moment.updateLocale('en', {
    longDateFormat : {
        LT: "h:mm A",
        LTS: "h:mm:ss A",
        L: "MM/DD/YYYY",
        l: "M/D/YYYY",
        LL: "MMMM Do YYYY",
        ll: "MMM D YYYY",
        LLL: "MMMM Do YYYY LT",
        lll: "MMM D YYYY LT",
        LLLL: "dddd, MMMM Do YYYY LT",
        llll: "ddd, MMM D YYYY LT"
    }
});
```

可以排除小写的 `l` 令牌，它们将会通过使用短令牌变体替换长令牌而自动创建。

```javascript
moment.updateLocale('en', {
    longDateFormat : {
        LT: "h:mm A",
        LTS: "h:mm:ss A",
        L: "MM/DD/YYYY",
        LL: "MMMM Do YYYY",
        LLL: "MMMM Do YYYY LT",
        LLLL: "dddd, MMMM Do YYYY LT"
    }
});
```
