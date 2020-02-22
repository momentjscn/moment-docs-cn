---
title: toISOString()
version: 2.8.0
signature: |
  moment.duration().toISOString();
---

返回 [ISO 8601 标准][ISO_8601_Durations]指定的字符串形式的时长。

```javascript
moment.duration(1, 'd').toISOString() // "P1D"
```

格式 ``PnYnMnDTnHnMnS`` 的说明：

<table class="table table-striped table-bordered">
  <tbody>
    <tr>
      <th>单位</th>
      <th>含义</th>
    </tr>
    <tr>
      <td>P</td>
      <td>_P_ 代表周期。 放置在时长表示的开始处。</td>
    </tr>
    <tr>
      <td>Y</td>
      <td>年</td>
    </tr>
    <tr>
      <td>M</td>
      <td>月</td>
    </tr>
    <tr>
      <td>D</td>
      <td>日</td>
    </tr>
    <tr>
      <td>T</td>
      <td>在时间分量之前的指示符。</td>
    </tr>
    <tr>
      <td>H</td>
      <td>小时</td>
    </tr>
    <tr>
      <td>M</td>
      <td>分钟</td>
    </tr>
    <tr>
      <td>S</td>
      <td>秒钟</td>
    </tr>
  </tbody>
</table>
