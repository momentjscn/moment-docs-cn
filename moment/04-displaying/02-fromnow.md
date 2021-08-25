---
title: fromNow()
version: 1.0.0
signature: |
  moment().fromNow();
  moment().fromNow(Boolean);
---


显示时间的常用方法是通过 `moment#fromNow` 处理。
有时称为时间间隔或相对时间。

```javascript
moment([2007, 0, 29]).fromNow(); // 4 年前
```

如果传入 `true`，则可以获得不带后缀的值。

```javascript
moment([2007, 0, 29]).fromNow();     // 4 年前
moment([2007, 0, 29]).fromNow(true); // 4 年
```

基本的字符串[由当前的语言环境自定义][moment-relativeTime]。
时间会舍入到最接近的秒数。

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
      <td>几秒前</td>
    </tr>
    <tr>
      <td><i>未设定</i></td>
      <td>ss</td>
      <td>44 秒前</td>
    </tr>
    <tr>
      <td>45 至 89 秒</td>
      <td>m</td>
      <td>1 分钟前</td>
    </tr>
    <tr>
      <td>90 秒至 44 分钟</td>
      <td>mm</td>
      <td>2 分钟前 ... 44 分钟前</td>
    </tr>
    <tr>
      <td>45 至 89 分钟</td>
      <td>h</td>
      <td>1 小时前</td>
    </tr>
    <tr>
      <td>90 分钟至 21 小时 </td>
      <td>hh</td>
      <td>2 小时前 ... 21 小时前</td>
    </tr>
    <tr>
      <td>22 至 35 小时</td>
      <td>d</td>
      <td>1 天前</td>
    </tr>
    <tr>
      <td>36 小时至 25 天</td>
      <td>dd</td>
      <td>2 天前 ... 25 天前</td>
    </tr>
    <tr>
      <td>26 至 45 天</td>
      <td>M</td>
      <td>1 个月前</td>
    </tr>
    <tr>
      <td>45 至 319 天</td>
      <td>MM</td>
      <td>2 个月前 ... 10 个月前</td>
    </tr>
    <tr>
      <td>320 至 547 天 (1.5 年)</td>
      <td>y</td>
      <td>1 年前</td>
    </tr>
    <tr>
      <td>548 天+</td>
      <td>yy</td>
      <td>2 年前 ... 20 年前</td>
    </tr>
  </tbody>
</table>

注意：从 **2.10.3** 版本开始，如果目标 moment 对象无效，则结果为本地化的无效日期字符串。

注意：`ss` 键新增于 **2.18.0**。
这是一个可选的阈值。
除非用户手动设置 ss 阈值，否则它将永远不会显示。
在设置 `ss` 阈值之前，它默认为 `s` 阈值减去 1（因此对用户不可见）的值。

