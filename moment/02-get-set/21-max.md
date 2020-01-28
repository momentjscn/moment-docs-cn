---
title: max()
version: 2.7.0
signature: |
  moment.max(Moment[,Moment...]);
  moment.max(Moment[]);
---

返回给定的 moment 实例的最大值（最远的未来）。

例如：

```javascript
var a = moment().subtract(1, 'day');
var b = moment().add(1, 'day');
moment.max(a, b);  // b

var friends = fetchFriends(); /* [{name: 'Dan', birthday: '11.12.1977'}, {name: 'Mary', birthday: '11.12.1986'}, {name: 'Stephan', birthday: '11.01.1993'}]*/
var friendsBirthDays = friends.map(function(friend){
    return moment(friend.birthday, 'DD.MM.YYYY');
});
moment.max(friendsBirthDays);  // '11.01.1993'
```

不带参数的函数会返回带有当前时间的 moment 实例。

从 **2.10.5** 版本开始，如果其中一个参数是无效的 moment ，则结果为无效的 moment。

```javascript
moment.max(moment(), moment.invalid()).isValid() === false
moment.max(moment.invalid(), moment()).isValid() === false
moment.max([moment(), moment.invalid()]).isValid() === false
moment.max([moment.invalid(), moment()]).isValid() === false
```
