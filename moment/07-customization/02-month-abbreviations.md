---
title: monthsShort
version: 1.0.0
signature: |
  // 从 2.12.0 开始
  moment.updateLocale('en', {
      monthsShort : String[]
  });
  moment.updateLocale('en', {
      monthsShort : Function
  });
  moment.updateLocale('en', {
      monthsShort : {
          format: String[],
          standalone : String[]
      }
  });
  // 从 2.11.0 开始
  moment.locale('en', {
      monthsShort : {
          format: String[],
          standalone : String[]
      }
  });
  // 从 2.8.1 至 2.11.2
  moment.locale('en', {
      monthsShort : String[]
  });
  moment.locale('en', {
      monthsShort : Function
  });

  // 废弃于 2.8.1
  moment.lang('en', {
      monthsShort : String[]
  });
  moment.lang('en', {
      monthsShort : Function
  });
---


`Locale#monthsShort` 应是月份缩写的数组。

```javascript
moment.updateLocale('en', {
    monthsShort : [
        "Jan", "Feb", "Mar", "Apr", "May", "Jun",
        "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"
    ]
});
```

与 `Locale#months` 一样，`Locale#monthsShort` 也可以是回调函数。

```javascript
moment.updateLocale('en', {
    monthsShort : function (momentToFormat, format) {
        if (/^MMMM/.test(format)) {
            return nominative[momentToFormat.month()];
        } else {
            return subjective[momentToFormat.month()];
        }
    }
});
```

注意：从 **2.11.0** 版本开始，与 `Locale#months` 一样，`Locale#monthsShort` 可以是具有 `standalone` 和 `format` 用例的对象。

```javascript
moment.updateLocale('en', {
    monthsShort : {
        format: 'янв_фев_мар_апр_мая_июня_июля_авг_сен_окт_ноя_дек'.split('_'),
        standalone: 'янв_фев_март_апр_май_июнь_июль_авг_сен_окт_ноя_дек'.split('_')
    }
});
```
