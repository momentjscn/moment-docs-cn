---
title: ordinal
version: 1.0.0
signature: |
  // 从 2.12.0 开始
  moment.updateLocale('en', {
      ordinal : Function
  });
  // 从 2.8.1 至 2.11.2
  moment.locale('en', {
      ordinal : Function
  });

  // 废弃于 2.8.1
  moment.lang('en', {
      ordinal : Function
  });
---


`Locale#ordinal` 应是一个返回给定数字序数的函数。

```javascript
moment.updateLocale('en', {
    ordinal : function (number, token) {
        var b = number % 10;
        var output = (~~ (number % 100 / 10) === 1) ? 'th' :
            (b === 1) ? 'st' :
            (b === 2) ? 'nd' :
            (b === 3) ? 'rd' : 'th';
        return number + output;
    }
});
```

从 **2.0.0** 开始，序数函数应同时返回数字和序数。以前仅返回序数。

从 **2.1.0** 开始，添加了令牌参数。它是要排序的令牌的字符串，例如：`M` 或 `d`。

有关序数的更多信息，参阅 [Wikipedia][wikipedia_ordinal_number]。

