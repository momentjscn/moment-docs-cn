---
title: week
version: 1.0.0
signature: |
  // 从 2.12.0 开始
  moment.updateLocale('en', {
      week : {
          dow : Int,
          doy : Int
       }
  });
  // 从 2.8.1 至 2.11.2
  moment.locale('en', {
      week : {
          dow : Int,
          doy : Int
      }
  });

  // 废弃于 2.8.1
  moment.lang('en', {
      week : {
          dow : Int,
          doy : Int
      }
  });
---

`Locale#week.dow` 应是代表星期中第一天的整数，0是星期日、1是星期一、...、6是星期六。

`Locale#week.doy` 应是整数。 
`doy` 与 `dow` 一起用于判断年份中的第一周。 
`doy` 的计算方式为 `7 + dow - janX`，其中 `janX` 是一月的第一天（必须属于年份中的第一周）。

```javascript
// ISO-8601，欧洲
moment.updateLocale("en", { week: {
  dow: 1, // 星期的第一天是星期一
  doy: 4  // 年份的第一周必须包含1月4日 (7 + 1 - 4)
}});

// 美国，加拿大
moment.updateLocale("en", { week: {
  dow: 0, // 星期的第一天是星期日
  doy: 6  // 年份的第一周必须包含1月1日 (7 + 0 - 1)
}});

// 许多阿拉伯国家
moment.updateLocale("en", { week: {
  dow: 6, // 星期的第一天是星期六
  doy: 12 // 年份的第一周必须包含1月1日 (7 + 6 - 1)
}});

// 也很常见
moment.updateLocale("en", { week: {
  dow: 1, // 星期的第一天是星期一
  doy: 7  // 年份的第一周必须包含1月1日 (7 + 1 - 1)
}});
```
