---
title: moment(String) 带格式
version: 1.0.0
signature: |
  moment(String, String);
  moment(String, String, String);
  moment(String, String, Boolean);
  moment(String, String, String, Boolean);
---


如果知道输入字符串的格式，则可以使用它来解析 moment。

```javascript
moment("12-25-1995", "MM-DD-YYYY");
```

解析器会忽略非字母和数字的字符，因此以下两个都将会返回相同的东西。

```javascript
moment("12-25-1995", "MM-DD-YYYY");
moment("12/25/1995", "MM-DD-YYYY");
```

解析令牌类似于 `moment＃format` 中使用的格式化令牌。

#### 年份、月份、日期的令牌

令牌区分大小写。

| 输入       | 示例          | 描述 |
| ----------- | ---------------- | ----------- |
| `YYYY`      | `2014`           | 4 或 2 位数字的年份 |
| `YY`        | `14`             | 2 位数字的年份 |
| `Y`         | `-25`            | 带有任意数字和符号的年份 |
| `Q`         | `1..4`           | 年份的季度。将月份设置为季度的第一个月 |
| `M MM`      | `1..12`          | 月份数字 |
| `MMM MMMM`  | `Jan..December`  | 区域设置中的月份名称，由 `moment.locale()` 设置 |
| `D DD`      | `1..31`          | 月的某天 |
| `Do`        | `1st..31st`      | 月的某天，带序数 |
| `DDD DDDD`  | `1..365`         | 年的某天 |
| `X`         | `1410715640.579` | Unix 时间戳 |
| `x`         | `1410715640579`  | Unix 毫秒时间戳 |

从版本 2.10.5 开始，`YYYY` 支持 2 位数字的年份，且会将其转换为接近 2000 的年份（与 `YY` 相同）。

`Y` 新增于 2.11.1 中。 
它将会匹配任何数字，有符号或无符号。 
对于非 4 位数字或公元前的年份很有用。 
它可以用于任何年份。


#### 周年、星期、工作日的令牌

对于这些，小写字母令牌使用区域设置感知的星期开始天数，而大写字母令牌使用 [ISO 星期日期][ISO_week_date]开始天数。

令牌区分大小写。

| 输入       | 示例          | 描述 |
| ----------- | ---------------- | ----------- |
| `gggg`      | `2014`           | 区域设置的 4 位数字的周年 |
| `gg`        | `14`             | 区域设置的 2 位数字的周年 |
| `w ww`      | `1..53`          | 区域设置的年的第几周 |
| `e`         | `0..6`           | 区域设置的星期几 |
| `ddd dddd`  | `Mon...Sunday`   | 区域设置的星期几的名称，由 `moment.locale()` 设置 |
| `GGGG`      | `2014`           | ISO 的 4 位数字的周年 |
| `GG`        | `14`             | ISO 的 2 位数字的周年 |
| `W WW`      | `1..53`          | ISO 的年的第几周 |
| `E`         | `1..7`           | ISO 的星期几 |


#### 区域设置感知的格式

使用 `LT LTS L LL LLL LLLL` 也可以使用区域设置感知的日期和时间格式。 
它们新增于 2.2.1 版本，其中 `LTS` 新增于 2.8.4。

令牌区分大小写。

| 输入          | 示例                               | 描述 |
| -------------- | ------------------------------------- | ----------- |
| `L`            | `04/09/1986`                          | 日期（以本地格式） |
| `LL`           | `September 4 1986`                    | 月份名称、月份日期、年份
| `LLL`          | `September 4 1986 8:30 PM`            | 月份名称、月份日期、年份、时间 |
| `LLLL`         | `Thursday, September 4 1986 8:30 PM`  | 星期几、月份名称、月份日期、年份、时间	 |
| `LT`           | `08:30 PM`                            | 时间（不含秒钟） |
| `LTS`          | `08:30:00 PM`                         | 时间（含秒钟） |

#### 小时、分钟、秒种、毫秒、偏移量的令牌

令牌区分大小写。

| 输入          | 示例  | 描述 |
| -------------- | -------- | ----------- |
| `H HH`         | `0..23`  | 小时（24 小时制） |
| `h hh`         | `1..12`  | 小时（使用 `a A` 的 12 小时制） |
| `k kk`         | `1..24`  | 小时（从 1 到 24 的 24 小时制） |
| `a A`          | `am pm`  | 上午或下午（单一字符 `a p` 也被视为有效） |
| `m mm`         | `0..59`  | 分钟 |
| `s ss`         | `0..59`  | 秒钟 |
| `S SS SSS`     | `0..999` | 带分数的秒钟 |
| `Z ZZ`         | `+12:00` | 从 UTC 偏移为 `+-HH:mm`、`+-HHmm` 或 `Z` |

从 2.10.5 版本开始：长度为 4 到 9 位的带分数的秒钟令牌可以解析任意数量的数字，但只会考虑前 3 个数（毫秒）。 
如果需要打印带有多位分数且想要消耗输入的时间，则使用它。

注意，仅在严格模式中解析时，提供的 `S` 字符的数量才有意义。 
在标准模式中，`S`、`SS`、`SSS`、`SSSS` 均等效，并解释为几分之一秒。 
例如，`.12` 始终为 120 毫秒，传入 `SS` 不会导致其被解释为 12 毫秒。

`Z ZZ` 新增于 1.2.0 版本。

`S SS SSS` 新增于 1.6.0 版本。

`X` 新增于 2.0.0 版本。

`k kk` 新增于 2.18.0 版本。

除非指定时区偏移量，否则解析字符串将会在当前时区中创建日期。

```js
moment("2010-10-20 4:30",       "YYYY-MM-DD HH:mm");   // 解析为当地时间 4:30。
moment("2010-10-20 4:30 +0000", "YYYY-MM-DD HH:mm Z"); // 解析为 UTC 时间 4:30。
```

如果 moment 解析的输入结果不存在，则 `moment＃isValid` 将会返回 false。

```js
moment("2010 13",           "YYYY MM").isValid();     // false（不是真实的月份）
moment("2010 11 31",        "YYYY MM DD").isValid();  // false（不是真实的日期）
moment("2010 2 29",         "YYYY MM DD").isValid();  // false（不是闰年）
moment("2010 notamonth 29", "YYYY MMM DD").isValid(); // false（不是真实的月份名称）
```

从 2.0.0 版本开始，可以将区域设置键作为第三个参数传给 `moment()` 和 `moment.utc()`。

```js
moment('2012 juillet', 'YYYY MMM', 'fr');
moment('2012 July',    'YYYY MMM', 'en');
```

Moment 的解析器非常宽松，这可能会导致不期望或意外的行为。

例如，可以观察到以下行为：

```javascript
moment('2016 is a date', 'YYYY-MM-DD').isValid() //true, 2016 被匹配。
```

在 2.13.0 之前，解析器会表现出以下行为。 
这已得到纠正。

```javascript
moment('I am spartacus', 'h:hh A').isValid();     //true - 'am' 和 'A' 标志匹配。
```

从 2.3.0 版本开始，可以为最后一个参数指定一个布尔值，以使 Moment 使用严格的解析。 
严格的解析要求格式和输入完全匹配，包括分隔符。

```javascript
moment('It is 2012-05-25', 'YYYY-MM-DD').isValid();       // true
moment('It is 2012-05-25', 'YYYY-MM-DD', true).isValid(); // false
moment('2012-05-25',       'YYYY-MM-DD', true).isValid(); // true
moment('2012.05.25',       'YYYY-MM-DD', true).isValid(); // false
```

可以同时使用区域设置和严格性。

```javascript
moment('2012-10-14', 'YYYY-MM-DD', 'fr', true);
```

严格的解析通常是最好的解析选项。 
有关选择严格还是宽松解析的更多信息，参阅[解析指南][guides_parsing]。

#### 解析两位数字的年份

默认情况下，68 之前的两位数字的年份会被假定是 1900 年代，而 68 或之后的年份则会被假定是 2000 年代。 
可以通过替换 `moment.parseTwoDigitYear` 方法来更改。 
该方法的唯一参数是包含用户输入的两位年份的字符串，并且应以整数形式返回年份。

```javascript
moment.parseTwoDigitYear = function(yearString) {
    return parseInt(yearString) + 2000;
}
```

#### 解析胶合的小时和分钟

从 2.11.0 版本开始，支持解析 `hmm`、`Hmm`、`hmmss` 和 `Hmmss`：

```javascript
moment("123", "hmm").format("HH:mm") === "01:23"
moment("1234", "hmm").format("HH:mm") === "12:34"
```
