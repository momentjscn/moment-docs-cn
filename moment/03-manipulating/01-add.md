---
title: add()
version: 1.0.0
signature: |
  moment().add(Number, String);
  moment().add(Duration);
  moment().add(Object);
---

通过增加时间来改变原始的 moment。

这是一个相当稳健的功能，可以为现有的 moment 增加时间。
若要增加时间，则传入要增加的时间的键、以及要增加的数量。

```javascript
moment().add(7, 'days');
```

如果对希望简短，也有一些快捷的键。

```javascript
moment().add(7, 'd');
```

<table class="table table-striped table-bordered">
  <tbody>
    <tr>
      <th>键</th>
      <th>快捷键</th>
    </tr>
    <tr>
      <td>years</td>
      <td>y</td>
    </tr>
    <tr>
      <td>quarters</td>
      <td>Q</td>
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

如果要同时增加多个不同的键，则可以将它们作为对象字面量传入。

```javascript
moment().add(7, 'days').add(1, 'months'); // 链式
moment().add({days:7,months:1}); // 对象字面量
```

数量没有上限，因此可以重载任何参数。

```javascript
moment().add(1000000, 'milliseconds'); // 一百万毫秒
moment().add(360, 'days'); // 360 天
```

#### 月份和年份的特殊考虑

如果原始日期的月份中的日期大于最终月份中的天数，则该月份中的日期将会更改为最终月份中的最后一天。

```javascript
moment([2010, 0, 31]);                  // 一月 31 号
moment([2010, 0, 31]).add(1, 'months'); // 二月 28 号
```

当增加跨越夏时制时间的时间时，还需要记住一些特殊的注意事项。
如果要增加年份、月份、周、或天，则原始的小时将始终与增加的小时匹配。

增加一个月会将指定的月数增加到日期。

```javascript
moment([2010, 1, 28]);                 // 二月 28 号
moment([2010, 1, 28]).add(1, 'month'); // 三月 28 号
```

```javascript
var m = moment(new Date(2011, 2, 12, 5, 0, 0)); // 美国夏令时开始的前一天
m.hours(); // 5
m.add(1, 'days').hours(); // 5
```

如果要增加小时、分钟、秒钟或毫秒，则会假设期望精确到小时，这将会导致不同的小时。

```javascript
var m = moment(new Date(2011, 2, 12, 5, 0, 0)); // 美国夏令时开始的前一天
m.hours(); // 5
m.add(24, 'hours').hours(); // 6（但可能需要先设置时区）
```

另外，可以使用[时长][durations]来增加时间。

```javascript
var duration = moment.duration({'days' : 1});
moment([2012, 0, 31]).add(duration); // 二月 1 号
```

在 **2.8.0** 版本之前，还支持 `moment#add(String, Number)` 语法。
不推荐使用它，而使用 `moment#add(Number, String)`。

```javascript
moment().add('seconds', 1); // 废弃于 2.8.0
moment().add(1, 'seconds');
```

从 **2.12.0** 版本开始，当为日期和月份传入小数时，它们会被四舍五入到最接近的整数。
星期、季度、年份会被转换到日期或月份，然后四舍五入到最接近的整数。

```javascript
moment().add(1.5, 'months') == moment().add(2, 'months')
moment().add(.7, 'years') == moment().add(8, 'months') //.7*12 = 8.4，取整到 8
```
