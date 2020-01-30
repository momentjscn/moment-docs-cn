---
title: toNow()
version: 2.10.3
signature: |
  moment().toNow();
  moment().toNow(Boolean);
---

显示时间的常用方法是通过 `moment#toNow` 处理。
有时称为时间间隔或相对时间。

这类似于 [`moment.fromNow`][moment.fromNow]，但给出相反的间隔：`a.fromNow() = - a.toNow()`。

这类似于 [`moment.to`][moment.to]，但在当前时间有特殊情况。
如果要控制间隔的两个端点，则使用 `moment.to`。

```javascript
moment([2007, 0, 29]).toNow(); // 4 年内
```

如果传入 `true`，则可以获取不带前缀的值。

```javascript
moment([2007, 0, 29]).toNow();     // 4 年内
moment([2007, 0, 29]).toNow(true); // 4 年
```

基本的字符串[由当前的语言环境自定义][moment-relativeTime]。

下表概述了每个时间长度显示的字符串的细分。

<table class="table table-striped table-bordered">
  <thead>
    <tr>
      <th>范围</th>
      <th>键</th>
      <th>样本输出</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0 至 44 秒</td>
      <td>s</td>
      <td>几秒内</td>
    </tr>
    <tr>
      <td>45 至 89 秒</td>
      <td>m</td>
      <td>1 分钟内</td>
    </tr>
    <tr>
      <td>90 秒至 44 分钟</td>
      <td>mm</td>
      <td>2 分钟内 ... 44 分钟内</td>
    </tr>
    <tr>
      <td>45 至 89 分钟</td>
      <td>h</td>
      <td>1 小时内</td>
    </tr>
    <tr>
      <td>90 分钟至 21 小时 </td>
      <td>hh</td>
      <td>2 小时内 ... 21 小时内</td>
    </tr>
    <tr>
      <td>22 至 35 小时</td>
      <td>d</td>
      <td>1 天内</td>
    </tr>
    <tr>
      <td>36 小时至 25 天</td>
      <td>dd</td>
      <td>2 天内 ... 25 天内</td>
    </tr>
    <tr>
      <td>26 至 45 天</td>
      <td>M</td>
      <td>1 个月内</td>
    </tr>
    <tr>
      <td>45 至 319 天</td>
      <td>MM</td>
      <td>2 个月内 ... 10 个月内</td>
    </tr>
    <tr>
      <td>320 至 547 天 (1.5 年)</td>
      <td>y</td>
      <td>1 年内</td>
    </tr>
    <tr>
      <td>548 天+</td>
      <td>yy</td>
      <td>2 年内 ... 20 年内</td>
    </tr>
  </tbody>
</table>

从 **2.10.3** 版本开始，如果目标 moment 对象无效，则结果为本地化的无效日期字符串。

