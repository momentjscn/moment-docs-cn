---
title: relativeTimeThreshold()
version: 2.7.0
signature: |
  moment.relativeTimeThreshold(unit);  // getter
  moment.relativeTimeThreshold(unit, limit);  // setter
---

`duration.humanize` 具有阈值，这些阈值定义何时将一个单位视为一分钟、一小时等。
例如，默认情况下，超过45秒会被视为一分钟，超过22小时会被视为一天，依此类推。
要更改这些截止值，则使用 `moment.relativeTimeThreshold(unit, limit)`，其中 unit 是 `ss`、`s`、`m`、`h`、`d`、`M` 之一。

<table>
  <tbody>
    <tr>
      <th>单位</th>
      <th>含义</th>
      <th>用法</th>
    </tr>
    <tr>
      <td>ss</td>
      <td>几秒钟</td>
      <td>被认为是秒钟的最少秒数。必须在设置 `s` 单位之后设置，或者不设置 `s` 单位。</td>
    </tr>
    <tr>
      <td>s</td>
      <td>秒钟</td>
      <td>被认为是一分钟的最少秒数。</td>
    </tr>
    <tr>
      <td>m</td>
      <td>分钟</td>
      <td>被认为是一小时的最少分钟数。</td>
    </tr>
    <tr>
      <td>h</td>
      <td>小时</td>
      <td>被认为是一天的最少小时数。</td>
    </tr>
    <tr>
      <td>d</td>
      <td>天</td>
      <td>被认为是一个月的最少天数。</td>
    </tr>
    <tr>
      <td>M</td>
      <td>月份</td>
      <td>被认为是一年的最少月份数。</td>
    </tr>
  </tbody>
</table>

```javascript
  // 检索现有的阈值。
  moment.relativeTimeThreshold('ss'); // 44
  moment.relativeTimeThreshold('s');  // 45
  moment.relativeTimeThreshold('m');  // 45
  moment.relativeTimeThreshold('h');  // 22
  moment.relativeTimeThreshold('d');  // 26
  moment.relativeTimeThreshold('M');  // 11

  // 设置新的阈值。
  moment.relativeTimeThreshold('ss', 3);
  moment.relativeTimeThreshold('s', 40);
  moment.relativeTimeThreshold('m', 40);
  moment.relativeTimeThreshold('h', 20);
  moment.relativeTimeThreshold('d', 25);
  moment.relativeTimeThreshold('M', 10);
```

注意：检索阈值新增于 **2.8.1**。

注意：检索与设置 `ss` 阈值新增于 **2.18.0**。

