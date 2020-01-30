---
title: calendar()
version: 1.3.0
signature: |
  moment().calendar();
  moment().calendar(referenceTime);
  moment().calendar(referenceTime, formats);  // 从 2.10.5 开始
---

日历时间显示相对于给定的 `referenceTime` 的时间（默认为现在），但与 `moment#fromNow` 略有不同。

`moment#calendar` 会根据日期与 `referenceTime` 的日期（默认为今天）的接近程度，使用不同的字符串格式化日期。

<table class="table table-striped table-bordered">
  <tr>
    <td>上个星期</td>
    <td>上星期一 2:30</td>
  </tr>
  <tr>
    <td>前一天</td>
    <td>昨天 2:30</td>
  </tr>
  <tr>
    <td>同一天</td>
    <td>今天 2:30</td>
  </tr>
  <tr>
    <td>下一天</td>
    <td>明天 2:30</td>
  </tr>
  <tr>
    <td>下个星期</td>
    <td>星期日 2:30</td>
  </tr>
  <tr>
    <td>其他</td>
    <td>7/10/2011</td>
  </tr>
</table>

这些字符串是本地化的，[可以自定义][moment-calendar]。

从 **2.10.5** 开始，moment 支持指定每次调用的日历输出格式：

```javascript
moment().calendar(null, {
    sameDay: '[今天]',
    nextDay: '[明天]',
    nextWeek: 'dddd',
    lastDay: '[昨天]',
    lastWeek: '[上个] dddd',
    sameElse: 'DD/MM/YYYY'
});
```

当 moment 与 `referenceTime` 相距超过一周时，则将 `sameElse` 用作格式。

注意：从 **2.14.0** 版本开始，日历的格式参数可以是一个在 moment 上下文中使用单个参数执行的回调：

```javascript
moment().calendar(null, {
  sameDay: function (now) {
    if (this.isBefore(now)) {
      return '[今天将会发生]';
    } else {
      return '[今天已发生]';
    }
    /* ... */
  }
});
```
