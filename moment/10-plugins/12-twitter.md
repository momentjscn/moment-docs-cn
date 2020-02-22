---
title: twitter
---


如果想尝试像 Twitter 一样格式化推文的时间，则可以使用 [@hijonathan][hijonathan] 的 [moment.twitter][moment.twitter] 插件。

这是显示人类可读的时间戳的长短版本的简单方法。

```javascript
moment().subtract(5, 'hours').twitterLong();
// 5 hours
```

是的，它可以进行智能多元化。

```javascript
moment().subtract(1, 'hour').twitterLong();
// 1 hour
```

还不够短吗？

```javascript
moment().subtract(6, 'days').twitterShort();
// 6d
```
