---
title: meridiemParse
version: 2.1.0
signature: |
  // 从 2.12.0 开始
  moment.updateLocale('en', {
      meridiemParse : RegExp
      isPM : Function
  });

  // 从 2.8.1 至 2.11.2
  moment.locale('en', {
      meridiemParse : RegExp
      isPM : Function
  });

  // 废弃于 2.8.1
  moment.lang('en', {
      meridiemParse : RegExp
      isPM : Function
  });
---


如果输入的字符是中午12点以后，则 `Locale#isPM` 应返回 true。
这用于解析 `a A` 令牌。

```javascript
moment.updateLocale('en', {
    isPM : function (input) {
        return ((input + '').toLowerCase()[0] === 'p');
    }
});
```

要配置应将哪些字符串解析为输入，则设置 `meridiemParse` 属性。

```javascript
moment.updateLocale('en', {
    meridiemParse : /[ap]\.?m?\.?/i
});
```
