---
title: feiertage
signature: |
  npm install moment-feiertage --save
---


这个 moment-feiertage 是一个 Moment.js 插件，用于确定日期是否为德国假期。
假期取自维基百科（德国）。
确定日期是否为假日有点复杂，因为宗教节日每年变化，在德国的 16 个州内也不同。


由 [DaniSchenk][DaniSchenk] 创建。

```js
var someDateInSomeStates = moment('2018-11-01').isHoliday(['BW', 'SH', 'TH']);
/* returns {
  allStates: false,
  holidayName: 'Allerheiligen',
  holidayStates: [ 'BW' ],
  testedStates: [ 'BW', 'SH', 'TH' ]
}*/
```

该仓库位于 [github.com/DaniSchenk/moment-feiertage][moment-feiertage]。
