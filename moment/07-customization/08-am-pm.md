---
title: meridiem
version: 1.6.0
signature: |
  // 从 2.12.0 开始
  moment.updateLocale('en', {
      meridiem : Function
  });
  // 从 2.8.1 至 2.11.2
  moment.locale('en', {
      meridiem : Function
  });

  // 废弃于 2.8.1
  moment.lang('en', {
      meridiem : Function
  });
---

如果语言环境使用 'am/pm'，则可以省略 `Locale#meridiem`，因为这些值是默认值。

如果语言环境需要对 am/pm 进行任何其他计算，则 `Locale#meridiem` 应是一个基于小时、分钟、和大写/小写返回正确字符串的回调函数。

```javascript
moment.updateLocale('zh-cn', {
    meridiem : function (hour, minute, isLowercase) {
        if (hour < 9) {
            return "早上";
        } else if (hour < 11 && minute < 30) {
            return "上午";
        } else if (hour < 13 && minute < 30) {
            return "中午";
        } else if (hour < 18) {
            return "下午";
        } else {
            return "晚上";
        }
    }
});
```

