---
title: recur
signature: |
  npm install moment-recur
---


如果需要处理重复的日期，则可以使用 Casey Trimm 的插件 `moment-recur`。

此插件将会允许你创建基于长度的间隔（天、周等）和基于日历的间隔（月份的日期、年份的月份等）。

它提供了一个 `matches` 函数来测试日期是否根据规则集重现，还提供了生成器函数来获取系列中的下一个和上一个日期。

仓库、文档和更多示例可以在 [github.com/c-trimm/moment-recur][moment-recur] 上找到。

```js
var interval = moment( "01/01/2014" ).recur().every(2).days(); // 长度间隔
interval.matches( "01/03/2014" ); // true
interval.next( 2, "L" ); // ["01/03/2014", "01/05/2014"]
interval.forget( "days" ); // 删除规则
interval.dayOfMonth( 10 ); // 日历间隔
interval.matches( "05/10/2014" ); // true
interval.previous( 2, "L" ); // ["12/10/2013", "11/10/2013"]
```
