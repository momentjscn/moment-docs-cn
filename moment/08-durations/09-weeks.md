---
title: weeks()
version: 1.6.0
signature: |
  moment.duration().weeks();
  moment.duration().asWeeks();
---

与时长的其他获取器一样，`moment.duration().weeks()` 用于获取星期数（0-4）。

`moment.duration().asWeeks()` 用于获取时长的长度（以星期为单位）。

与时长的其他获取器不同，星期数获取器是作为天数的子集，且不会从天数中扣除。

注意：以星期为单位的时长的长度定义为 7 天。

