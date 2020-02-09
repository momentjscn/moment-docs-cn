---
title: duration()
version: 1.6.0
signature: |
  moment.duration(Number, String);
  moment.duration(Number);
  moment.duration(Object);
  moment.duration(String);
---

要创建时长，则调用 `moment.duration()`，并以毫秒为单位。

```javascript
moment.duration(100); // 100 毫秒
```

如果要使用毫秒以外的其他度量单位来创建 moment，则也可以传入度量单位。

```javascript
moment.duration(2, 'seconds');
moment.duration(2, 'minutes');
moment.duration(2, 'hours');
moment.duration(2, 'days');
moment.duration(2, 'weeks');
moment.duration(2, 'months');
moment.duration(2, 'years');
```

同样，`moment#add` 和 `moment#subtract`的简写在这里也适用。

<table class="table table-striped table-bordered">
  <tbody>
    <tr>
      <th>键</th>
      <th>简写</th>
    </tr>
    <tr>
      <td>years</td>
      <td>y</td>
    </tr>
    <tr>
      <td>months</td>
      <td>M</td>
    </tr>
    <tr>
      <td>weeks</td>
      <td>w</td>
    </tr>
    <tr>
      <td>days</td>
      <td>d</td>
    </tr>
    <tr>
      <td>hours</td>
      <td>h</td>
    </tr>
    <tr>
      <td>minutes</td>
      <td>m</td>
    </tr>
    <tr>
      <td>seconds</td>
      <td>s</td>
    </tr>
    <tr>
      <td>milliseconds</td>
      <td>ms</td>
    </tr>
  </tbody>
</table>

与 `moment#add` 相似，如果需要多个不同的度量单位，则可以传入值的对象。

```javascript
moment.duration({
    seconds: 2,
    minutes: 2,
    hours: 2,
    days: 2,
    weeks: 2,
    months: 2,
    years: 2
});
```

从 **2.1.0** 开始，moment 支持解析 ASP.NET 风格的时间跨度。
支持以下格式。

格式是以冒号分隔的小时、分钟、秒钟的字符串，例如 `23:59:59`。
天数可以加上点分隔符，如 `7.23:59:59。
还支持部分秒数如 `23:59:59.999`。

```javascript
moment.duration('23:59:59');
moment.duration('23:59:59.999');
moment.duration('7.23:59:59.999');
moment.duration('23:59'); // 新增于 2.3.0
```

从 **2.3.0** 开始，moment 还支持解析 [ISO 8601][ISO_8601_Time_intervals] 时长。

```javascript
moment.duration('P1Y2M3DT4H5M6S');
moment.duration('P1M');
```

从 **2.11.0** 开始，支持时长的格式字符串，其中天数和剩下的时间之间有空格。

```javascript
moment.duration('7 23:59:59.999');
```

从 **2.13.0** 开始，解析时长时支持混合的负号和正号。

```javascript
moment.duration('PT-6H3M')
```

从 **2.18.0** 开始，支持无效的时长，类似于无效的时刻。
要创建无效的时长，可以为单位的值传入 `NaN`。

在即将发布的版本中，预期无效的时长可以覆盖更多情况（例如单位的空值）。

```javascript
moment.duration(NaN);
moment.duration(NaN, 'days');
moment.duration.invalid();
```