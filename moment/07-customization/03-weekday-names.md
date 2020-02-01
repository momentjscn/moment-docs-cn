---
title: weekdays
version: 1.0.0
signature: |
  // 从 2.12.0 版本开始
  moment.updateLocale('en', {
      weekdays : String[]
  });
  moment.updateLocale('en', {
      weekdays : Function
  });
  moment.updateLocale('en', {
      weekdays : {
          standalone : String[],
          format : String[],
          isFormat : RegExp
      }
  });
  // 从 2.11.0 版本开始
  moment.locale('en', {
      weekdays : {
          standalone : String[],
          format : String[],
          isFormat : Boolean
      }
  });
  // 从 2.8.1 至 2.11.2 版本
  moment.locale('en', {
      weekdays : String[]
  });
  moment.locale('en', {
      weekdays : Function
  });

  // 废弃于 2.8.1 版本
  moment.lang('en', {
      weekdays : String[]
  });
  moment.lang('en', {
      weekdays : Function
  });

---


`Locale#weekdays` 应是工作日名称的数组。

```javascript
moment.updateLocale('en', {
    weekdays : [
        "Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"
    ]
});
```

`Locale#weekdays` 也可以是回调函数。

```javascript
moment.updateLocale('en', {
    weekdays : function (momentToFormat, format) {
        return weekdays[momentToFormat.day()];
    }
});
```

注意：从 **2.11.0** 版本开始，format/standalone 用例也可以传入。 
`isFormat` 将会用于完整的格式字符串，以判断要使用的格式。

```javascript
moment.updateLocale('en', {
    weekdays : {
        standalone: 'Воскресенье_Понедельник_Вторник_Среда_Четверг_Пятница_Суббота'.split('_'),
        format: 'Воскресенье_Понедельник_Вторник_Среду_Четверг_Пятницу_Субботу'.split('_'),
        isFormat: /\[ ?[Вв] ?(?:прошлую|следующую|эту)? ?\] ?dddd/
    }
});
```
