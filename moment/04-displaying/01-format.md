---
title: format()
version: 1.0.0
signature: |
  moment().format();
  moment().format(String);
---

这是最稳健的显示选项。
它接受一串令牌并将其替换为其相应的值。

```javascript
moment().format();                                // "2014-09-08T08:02:17-05:00" (ISO 8601，无小数秒钟)
moment().format("dddd, MMMM Do YYYY, h:mm:ss a"); // "Sunday, February 14th 2010, 3:25:50 pm"
moment().format("ddd, hA");                       // "Sun, 3PM"
moment('gibberish').format('YYYY MM DD');         // "Invalid date"
```

<table class="table table-striped table-bordered">
  <tbody>
    <tr>
      <th></th>
      <th>令牌</th>
      <th>输出</th>
    </tr>
    <tr>
      <td><b>月份</b></td>
      <td>M</td>
      <td>1 2 ... 11 12</td>
    </tr>
    <tr>
      <td></td>
      <td>Mo</td>
      <td>1st 2nd ... 11th 12th</td>
    </tr>
    <tr>
      <td></td>
      <td>MM</td>
      <td>01 02 ... 11 12</td>
    </tr>
    <tr>
      <td></td>
      <td>MMM</td>
      <td>Jan Feb ... Nov Dec</td>
    </tr>
    <tr>
      <td></td>
      <td>MMMM</td>
      <td>January February ... November December</td>
    </tr>
    <tr>
      <td><b>季度</b></td>
      <td>Q</td>
      <td>1 2 3 4</td>
    </tr>
    <tr>
      <td></td>
      <td>Qo</td>
      <td>1st 2nd 3rd 4th</td>
    </tr>
    <tr>
      <td><b>月份的日期</b></td>
      <td>D</td>
      <td>1 2 ... 30 31</td>
    </tr>
    <tr>
      <td></td>
      <td>Do</td>
      <td>1st 2nd ... 30th 31st</td>
    </tr>
    <tr>
      <td></td>
      <td>DD</td>
      <td>01 02 ... 30 31</td>
    </tr>
    <tr>
      <td><b>年份的日期</b></td>
      <td>DDD</td>
      <td>1 2 ... 364 365</td>
    </tr>
    <tr>
      <td></td>
      <td>DDDo</td>
      <td>1st 2nd ... 364th 365th</td>
    </tr>
    <tr>
      <td></td>
      <td>DDDD</td>
      <td>001 002 ... 364 365</td>
    </tr>
    <tr>
      <td><b>星期几</b></td>
      <td>d</td>
      <td>0 1 ... 5 6</td>
    </tr>
    <tr>
      <td></td>
      <td>do</td>
      <td>0th 1st ... 5th 6th</td>
    </tr>
    <tr>
      <td></td>
      <td>dd</td>
      <td>Su Mo ... Fr Sa</td>
    </tr>
    <tr>
      <td></td>
      <td>ddd</td>
      <td>Sun Mon ... Fri Sat</td>
    </tr>
    <tr>
      <td></td>
      <td>dddd</td>
      <td>Sunday Monday ... Friday Saturday</td>
    </tr>
    <tr>
      <td><b>星期几（区域设置）</b></td>
      <td>e</td>
      <td>0 1 ... 5 6</td>
    </tr>
    <tr>
      <td><b>星期几（ISO）</b></td>
      <td>E</td>
      <td>1 2 ... 6 7</td>
    </tr>
    <tr>
      <td><b>年份的星期</b></td>
      <td>w</td>
      <td>1 2 ... 52 53</td>
    </tr>
    <tr>
      <td></td>
      <td>wo</td>
      <td>1st 2nd ... 52nd 53rd</td>
    </tr>
    <tr>
      <td></td>
      <td>ww</td>
      <td>01 02 ... 52 53</td>
    </tr>
    <tr>
      <td><b>年份的星期（ISO）</b></td>
      <td>W</td>
      <td>1 2 ... 52 53</td>
    </tr>
    <tr>
      <td></td>
      <td>Wo</td>
      <td>1st 2nd ... 52nd 53rd</td>
    </tr>
    <tr>
      <td></td>
      <td>WW</td>
      <td>01 02 ... 52 53</td>
    </tr>
    <tr>
      <td><b>年份</b></td>
      <td>YY</td>
      <td>70 71 ... 29 30</td>
    </tr>
    <tr>
      <td></td>
      <td>YYYY</td>
      <td>1970 1971 ... 2029 2030</td>
    </tr>
      <tr>
      <td></td>
      <td>Y</td>
      <td>1970 1971 ... 9999 +10000 +10001
        <br />
	注意：对于 9999 年以后的日期，这符合 ISO 8601 标准。
      </td>
    </tr>
    <tr>
      <td><b>周年</b></td>
      <td>gg</td>
      <td>70 71 ... 29 30</td>
    </tr>
    <tr>
      <td></td>
      <td>gggg</td>
      <td>1970 1971 ... 2029 2030</td>
    </tr>
    <tr>
      <td><b>周年（ISO）</b></td>
      <td>GG</td>
      <td>70 71 ... 29 30</td>
    </tr>
    <tr>
      <td></td>
      <td>GGGG</td>
      <td>1970 1971 ... 2029 2030</td>
    </tr>
    <tr>
      <td><b>子午线</b></td>
      <td>A</td>
      <td>AM PM</td>
    </tr>
    <tr>
      <td></td>
      <td>a</td>
      <td>am pm</td>
    </tr>
    <tr>
      <td><b>小时</b></td>
      <td>H</td>
      <td>0 1 ... 22 23</td>
    </tr>
    <tr>
      <td></td>
      <td>HH</td>
      <td>00 01 ... 22 23</td>
    </tr>
    <tr>
      <td></td>
      <td>h</td>
      <td>1 2 ... 11 12</td>
    </tr>
    <tr>
      <td></td>
      <td>hh</td>
      <td>01 02 ... 11 12</td>
    </tr>
    <tr>
      <td></td>
      <td>k</td>
      <td>1 2 ... 23 24</td>
    </tr>
    <tr>
      <td></td>
      <td>kk</td>
      <td>01 02 ... 23 24</td>
    </tr>
    <tr>
      <td><b>分钟</b></td>
      <td>m</td>
      <td>0 1 ... 58 59</td>
    </tr>
    <tr>
      <td></td>
      <td>mm</td>
      <td>00 01 ... 58 59</td>
    </tr>
    <tr>
      <td><b>秒钟</b></td>
      <td>s</td>
      <td>0 1 ... 58 59</td>
    </tr>
    <tr>
      <td></td>
      <td>ss</td>
      <td>00 01 ... 58 59</td>
    </tr>
    <tr>
      <td><b>小数秒钟</b></td>
      <td>S</td>
      <td>0 1 ... 8 9</td>
    </tr>
    <tr>
      <td></td>
      <td>SS</td>
      <td>00 01 ... 98 99</td>
    </tr>
    <tr>
      <td></td>
      <td>SSS</td>
      <td>000 001 ... 998 999</td>
    </tr>
    <tr>
      <td></td>
      <td>SSSS ... SSSSSSSSS</td>
      <td>000[0..] 001[0..] ... 998[0..] 999[0..]</td>
    </tr>
    <tr>
      <td><b>时区</b></td>
      <td>z or zz</td>
      <td>
        EST CST ... MST PST
        <br/>
	注意：从 <b>1.6.0</b> 版本开始，z/zz 格式的令牌已从普通的 moment 对象中弃用。
	<a href="https://github.com/moment/moment/issues/162">在此处了解更多信息</a>。
	但是，如果将特定时区与 moment-timezone 插件一起使用，它们会起作用。
      </td>
    </tr>
    <tr>
      <td></td>
      <td>Z</td>
      <td>-07:00 -06:00 ... +06:00 +07:00</td>
    </tr>
    <tr>
      <td></td>
      <td>ZZ</td>
      <td>
        -0700 -0600 ... +0600 +0700
      </td>
    </tr>
    <tr>
      <td><b>Unix 时间戳</b></td>
      <td>X</td>
      <td>1360013296</td>
    </tr>
    <tr>
      <td><b>Unix 毫秒时间戳</b></td>
      <td>x</td>
      <td>1360013296123</td>
    </tr>
  </tbody>
</table>

`X` 新增于 **2.0.0**。

`e E gg gggg GG GGGG` 新增于 **2.1.0**。

`x` 新增于 **2.8.4**。

`SSSS` 至 `SSSSSSSSS` 新增于 **2.10.5**。
它们会显示 3 位有效数字，其余部分用零填充。

`k` 和 `kk` 新增于 **2.13.0**。

#### 本地化格式

由于首选的格式会根据区域设置而有所不同，因此有一些令牌可用于根据区域设置格式 moment。

同一格式有大小写变体。
小写版本旨在作为大写版本的简化版本。

<table class="table table-striped table-bordered">
  <tbody>
    <tr>
      <td><b>时间</b></td>
      <td>LT</td>
      <td>8:30 PM</td>
    </tr>
    <tr>
      <td><b>带秒钟的时间</b></td>
      <td>LTS</td>
      <td>8:30:25 PM</td>
    </tr>
    <tr>
      <td><b>月份数字，月份日期，年份</b></td>
      <td>L</td>
      <td>09/04/1986</td>
    </tr>
    <tr>
      <td></td>
      <td>l</td>
      <td>9/4/1986</td>
    </tr>
    <tr>
      <td><b>月份名称，月份日期，年份</b></td>
      <td>LL</td>
      <td>September 4, 1986</td>
    </tr>
    <tr>
      <td></td>
      <td>ll</td>
      <td>Sep 4, 1986</td>
    </tr>
    <tr>
      <td><b>月份名称，月份日期，年份，时间</b></td>
      <td>LLL</td>
      <td>September 4, 1986 8:30 PM</td>
    </tr>
    <tr>
      <td></td>
      <td>lll</td>
      <td>Sep 4, 1986 8:30 PM</td>
    </tr>
    <tr>
      <td><b>月份名称，月份日期，星期几，年份，时间</b></td>
      <td>LLLL</td>
      <td>Thursday, September 4, 1986 8:30 PM</td>
    </tr>
    <tr>
      <td></td>
      <td>llll</td>
      <td>Thu, Sep 4, 1986 8:30 PM</td>
    </tr>
  </tbody>
</table>

`l ll lll llll` 在 **2.0.0** 中可用。
`LTS` 新增于 **2.8.4**。

#### 转义字符

要转义格式字符串中的字符，可以将字符包装在方括号中。

```javascript
moment().format('[今天] dddd'); // '今天 Sunday'
```

#### 与 LDML 的异同

注意：虽然这些日期格式与 LDML 日期格式非常相似，但是在月份的日期、年份的日期、星期几等方面存在一些细微的差异。

有关跨不同区域设置的一些不同的日期格式令牌的详细信息，参阅[日期格式令牌的图表][date_formatting_tokens_chart]。

#### 格式化速度

要与其他库比较 Moment.js 的格式化速度，请差异[与其他库的比较][date_formatting_comparison]。


#### 其他令牌

如果更习惯使用 strftime 而不是类似 LDML 的解析令牌，则可以使用 Ben Oakes 的插件 [benjaminoakes/moment-strftime][moment-strftime]。

#### 默认的格式

不使用格式调用 `moment#format` 将会默认为 `moment.defaultFormat`。
开箱即用的 `moment.defaultFormat` 是 ISO8601 格式 `YYYY-MM-DDTHH:mm:ssZ`。

从 **2.13.0** 版本开始，当在 UTC 模式中时，默认的格式由 `moment.defaultFormatUtc` 管理的，其格式是 `YYYY-MM-DDTHH:mm:ss[Z]`。
这会返回 ``Z`` 作为偏移量，而不是 ``+00:00``。

在某些情况下，本地时区（例如 `Atlantic/Reykjavik`）可能具有零偏移量，且将会被视为 UTC。
在这种情况下，将 `moment.defaultFormat` 和 `moment.defaultFormatUtc` 设置为使用相同的格式可能很有用。

更改 `moment.defaultFormat` 的值仅会影响格式化，而不会影响解析。
例如：

```javascript
moment.defaultFormat = "DD.MM.YYYY HH:mm";
// 使用 .toDate() 解析。
moment('20.07.2018 09:19').toDate() // Invalid date
// 使用新的 defaultFormat 格式化日期字符串，然后解析。
moment('20.07.2018 09:19', moment.defaultFormat).toDate() // Fri Jul 20 2018 09:19:00 GMT+0300
```
