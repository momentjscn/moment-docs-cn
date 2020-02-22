---
title: business
signature: |
  npm install moment-business
---

这是一个 Moment.js 库，允许 Moment 在西方工作周中进行操作：7 天工作周，其中周六和周日为非工作日。

例如，

```js
import business from 'moment-business';

// 如果 moment 是周一至周五，则为 true，否则为 false。
business.isWeekDay(someMoment);

// 增加五个工作日到 Moment。
business.addWeekDays(someMoment, 5);
```

该仓库位于 [github.com/jmeas/moment-business][moment-business]。

