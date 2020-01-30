---
title: inspect()
version: 2.16.0
signature: |
  moment().inspect();
---

返回机器可读的字符串，可以对其进行评估以产生相同的 moment。
由于其名称，它还用于节点交互式 shell 中以显示对象。

```javascript
moment().inspect() // 'moment("2016-11-09T22:23:27.861")'
moment.utc().inspect() // 'moment.utc("2016-11-10T06:24:10.638+00:00")'
moment.parseZone('2016-11-10T06:24:12.958+05:00').inspect() // 'moment.parseZone("2016-11-10T06:24:12.958+05:00")'
moment(new Date('nope')).inspect() // 'moment.invalid(/* Invalid Date */)'
moment('blah', 'YYYY').inspect() // 'moment.invalid(/* blah */)'
```

注意：此函数主要用于调试，并非所有情况都经过精确处理。

