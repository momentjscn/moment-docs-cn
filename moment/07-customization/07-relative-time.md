---
title: relativeTime
version: 1.0.0
signature: |
  // 从 2.12.0 开始
  moment.updateLocale('en', {
      relativeTime : Object
  });
  // 从 2.8.1 至 2.11.2
  moment.locale('en', {
      relativeTime : Object
  });

  // 废弃于 2.8.1
  moment.lang('en', {
      relativeTime : Object
  });
---


`Locale#relativeTime` 应是用于 `moment#from` 的替换字符串的对象。

```javascript
moment.updateLocale('en', {
    relativeTime : {
        future: "in %s",
        past:   "%s ago",
        s  : 'a few seconds',
        ss : '%d seconds',
        m:  "a minute",
        mm: "%d minutes",
        h:  "an hour",
        hh: "%d hours",
        d:  "a day",
        dd: "%d days",
        M:  "a month",
        MM: "%d months",
        y:  "a year",
        yy: "%d years"
    }
});
```

`Locale#relativeTime.future` 指向未来日期的前缀/后缀，而 `Locale#relativeTime.past` 则指向过去日期的前缀/后缀。
对于所有其他字符，单个字符指向单数，而双字符指向复数。

如果语言环境需要对令牌进行其他处理，则可以使用以下签名将令牌设置为函数。
该函数应返回一个字符串。

<!-- skip-example -->

```javascript
function (number, withoutSuffix, key, isFuture) {
    return string;
}
```

`key` 参数指向 `Locale#relativeTime ` 对象中的替换键。（例如 `s m mm h` 等）

`number` 参数指向该键的单位数。
对于 `m`，该数字是分钟数，以此类推。

如果不带后缀显示令牌，则 `withoutSuffix` 参数将会为 true，如果带后缀显示令牌，则为 false。（之所以使用逻辑倒置，是因为默认的行为是显示后缀。）

如果要使用未来的后缀/前缀，则 `isFuture` 参数将会为 true，如果要使用过去的前缀/后缀，则为 false。

