---
title: months
version: 1.0.0
signature: |
  // 从 2.12.0 开始
  moment.updateLocale('en', {
      months : String[]
  });
  moment.updateLocale('en', {
      months : Function
  });
  moment.updateLocale('en', {
      months : {
          format : String[],
          standalone : String[]
      }
  });
  // 从 2.11.0 开始
  moment.locale('en', {
      months : {
          format : String[],
          standalone : String[]
      }
  });
  // 从 2.8.1 至 2.11.2
  moment.locale('en', {
      months : String[]
  });
  moment.locale('en', {
      months : Function
  });

  // 废弃于 2.8.1
  moment.lang('en', {
      months : String[]
  });
  moment.lang('en', {
      months : Function
  });
---


`Locale#months` 应是月份名称的数组。

```javascript
moment.updateLocale('en', {
    months : [
        "January", "February", "March", "April", "May", "June", "July",
        "August", "September", "October", "November", "December"
    ]
});
```

如果需要更多处理来计算月份的名称（例如，如果不同格式的语法不同），则 `Locale#months` 可以是具有以下签名的函数。
它应始终返回月份的名称。

```javascript
moment.updateLocale('en', {
    months : function (momentToFormat, format) {
        // momentToFormat 是当前正在被格式化的 moment。
        // format 是格式化字符串。
        if (/^MMMM/.test(format)) { // 如果格式以 'MMMM' 开头。
            return nominative[momentToFormat.month()];
        } else {
            return subjective[momentToFormat.month()];
        }
    }
});
```

从 **2.11.0** 版本开始，月份也可以是一个对象，指定 `standalone` 和 `format` 的形式（主格和宾格）。
在格式上运行以检查是否使用 `format` 形式的正则表达式是 `/D[oD]?(\[[^\[\]]*\]|\s+)+MMMM?/`。
从 **2.14.0** 版本开始，可以使用 `isFormat` 键指定另一个。

```javascript
moment.updateLocale('en', {
    months : {
         format: 'sausio_vasario_kovo_balandžio_gegužės_birželio_liepos_rugpjūčio_rugsėjo_spalio_lapkričio_gruodžio'.split('_'),
         standalone: 'sausis_vasaris_kovas_balandis_gegužė_birželis_liepa_rugpjūtis_rugsėjis_spalis_lapkritis_gruodis'.split('_'),
         isFormat: /D[oD]?(\[[^\[\]]*\]|\s+)+MMMM?|MMMM?(\[[^\[\]]*\]|\s+)+D[oD]?/  // from 2.14.0
    }
});
```
