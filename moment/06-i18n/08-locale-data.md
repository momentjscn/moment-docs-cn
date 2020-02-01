---
title: localeData()
version: 2.8.0
signature: |
  localeData = moment.localeData()
  localeData.months(Moment)
  localeData.months()
  localeData.monthsShort(Moment)
  localeData.monthsShort()
  localeData.monthsParse(String)
  localeData.weekdays(Moment)
  localeData.weekdays()
  localeData.weekdays(Boolean)      ## 新增于 2.24.0，按语言环境对工作日进行排序。
  localeData.weekdaysShort(Moment)
  localeData.weekdaysShort()
  localeData.weekdaysShort(Boolean) ## 新增于 2.24.0，按语言环境对工作日进行排序。
  localeData.weekdaysMin(Moment)
  localeData.weekdaysMin()
  localeData.weekdaysMin(Boolean)   ## 新增于 2.24.0，按语言环境对工作日进行排序。
  localeData.weekdaysParse(String)
  localeData.longDateFormat(String)
  localeData.isPM(String)
  localeData.meridiem(Number, Number, Boolean)
  localeData.calendar(String, Moment)
  localeData.relativeTime(Number, Boolean, String, Boolean)
  localeData.pastFuture(Number, String)
  localeData.ordinal(Number)
  localeData.preparse(String)
  localeData.postformat(String)
  localeData.week(Moment)
  localeData.invalidDate()
  localeData.firstDayOfWeek()
  localeData.firstDayOfYear()
---


可以通过 `moment.localeData(key)` 函数访问当前加载的语言环境的属性。
它返回当前语言环境或具有给定键的语言环境：

```javascript
// 获取当前的语言环境
var currentLocaleData = moment.localeData();
var frLocaleData = moment.localeData('fr');
```

返回的对象具有以下方法：

```javascript
localeData.months(aMoment);  // aMoment 的完整月份名称
localeData.monthsShort(aMoment);  // aMoment 的简短月份名称
localeData.monthsParse(longOrShortMonthString);  // 返回输入的月份 id (0 至 11)
localeData.weekdays(aMoment);  // aMoment 的完整工作日名称
localeData.weekdaysShort(aMoment);  // aMoment 的简短工作日名称
localeData.weekdaysMin(aMoment);  // aMoment 的最小工作日名称
localeData.weekdaysParse(minShortOrLongWeekdayString);  // 返回输入的工作日 id (0 至 6)
localeData.longDateFormat(dateFormat);  // 返回缩写的日期时间格式（LT、L、LL 等）的完整格式
localeData.isPM(amPmString);  // 如果 amPmString 代表 PM，则返回 true
localeData.meridiem(hours, minutes, isLower);  // 返回大写/小写的特定日期时间的 am/pm 字符串
localeData.calendar(key, aMoment);  // 返回用于日历表示的格式。键是 'sameDay'、'nextDay'、'lastDay'、'nextWeek'、'prevWeek'、'sameElse' 之一
localeData.relativeTime(number, withoutSuffix, key, isFuture);  // 返回相对时间的字符串，键是 's'、'm'、'mm'、'h'、'hh'、'd'、'dd'、'M'、'MM'、'y'、'yy' 之一。当 number 为 1 时为单个字母
localeData.pastFuture(diff, relTime);  // 根据差异将 relTime 字符串转换为过去或未来的字符串
localeData.ordinal(number);  // 将数字转换为序数字符串 1-> 1st
localeData.preparse(str);  // 在解析每个输入字符串之前调用
localeData.postformat(str);  // 在格式化每个字符串后调用
localeData.week(aMoment);  // 返回 aMoment 的周年
localeData.invalidDate();  // 返回 'Invalid date' 的翻译
localeData.firstDayOfWeek();  // 0-6 (星期日至星期六)
localeData.firstDayOfYear();  // 0-15 用于判断年份的第一周
```

有关 `firstDayOfYear` 的详细信息可以在[自定义][moment_dow-doy]章节中查看。

