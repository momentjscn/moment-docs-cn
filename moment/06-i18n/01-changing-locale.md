---
title: 设置语言环境 (全局)
version: 1.0.0
signature: |
  // 从 2.8.1 开始
  moment.locale(String);
  moment.locale(String[]);
  moment.locale(String, Object);

  // 废弃于 2.8.1
  moment.lang(String);
  moment.lang(String[]);
  moment.lang(String, Object);
---

默认情况下，Moment.js 随附英语（美国）语言环境字符串。
如果需要其他语言环境，则可以将它们加载到 Moment.js 中以供随后使用。

要加载语言环境，则将键和字符串值传给 `moment.locale`。

可以在[自定义][moment_customization]章节中找到有关语言环境包的各个部分的更多详细信息。

```javascript
moment.locale('fr', {
    months : 'janvier_février_mars_avril_mai_juin_juillet_août_septembre_octobre_novembre_décembre'.split('_'),
    monthsShort : 'janv._févr._mars_avr._mai_juin_juil._août_sept._oct._nov._déc.'.split('_'),
    monthsParseExact : true,
    weekdays : 'dimanche_lundi_mardi_mercredi_jeudi_vendredi_samedi'.split('_'),
    weekdaysShort : 'dim._lun._mar._mer._jeu._ven._sam.'.split('_'),
    weekdaysMin : 'Di_Lu_Ma_Me_Je_Ve_Sa'.split('_'),
    weekdaysParseExact : true,
    longDateFormat : {
        LT : 'HH:mm',
        LTS : 'HH:mm:ss',
        L : 'DD/MM/YYYY',
        LL : 'D MMMM YYYY',
        LLL : 'D MMMM YYYY HH:mm',
        LLLL : 'dddd D MMMM YYYY HH:mm'
    },
    calendar : {
        sameDay : '[Aujourd’hui à] LT',
        nextDay : '[Demain à] LT',
        nextWeek : 'dddd [à] LT',
        lastDay : '[Hier à] LT',
        lastWeek : 'dddd [dernier à] LT',
        sameElse : 'L'
    },
    relativeTime : {
        future : 'dans %s',
        past : 'il y a %s',
        s : 'quelques secondes',
        m : 'une minute',
        mm : '%d minutes',
        h : 'une heure',
        hh : '%d heures',
        d : 'un jour',
        dd : '%d jours',
        M : 'un mois',
        MM : '%d mois',
        y : 'un an',
        yy : '%d ans'
    },
    dayOfMonthOrdinalParse : /\d{1,2}(er|e)/,
    ordinal : function (number) {
        return number + (number === 1 ? 'er' : 'e');
    },
    meridiemParse : /PD|MD/,
    isPM : function (input) {
        return input.charAt(0) === 'M';
    },
    // 如果子午线单位未在12左右分开，则实现此函数（以 locale/id.js 为例）。
    // meridiemHour : function (hour, meridiem) {
    //     return /* 0-23 小时，给定的子午线令牌和 1-12小时 */ ;
    // },
    meridiem : function (hours, minutes, isLower) {
        return hours < 12 ? 'PD' : 'MD';
    },
    week : {
        dow : 1, // 星期一是一周的第一天。
        doy : 4  // 用于判断一年中的第一周。
    }
});
```

有关 `week.dow` 和 `week.doy` 的详细信息可以在[自定义][moment_dow-doy]章节中找到。

加载语言环境之后，则它会成为活动的语言环境。
要更改活动的语言环境，只需使用已加载的语言环境的键调用 `moment.locale`。

```javascript
moment.locale('fr');
moment(1316116057189).fromNow(); // il y a une heure
moment.locale('en');
moment(1316116057189).fromNow(); // an hour ago
```

从 **2.21.0** 开始，如果语言环境不可用，则 Moment 将会 `console.warn`。

从 **2.8.0** 开始，更改全局的语言环境不会影响已存在的实例。

```javascript
moment.locale('fr');
var m = moment(1316116057189);
m.fromNow(); // il y a une heure

moment.locale('en');
m.fromNow(); // il y a une heure
moment(1316116057189).fromNow(); // an hour ago
```

`moment.locale` 返回使用的语言环境。
这很有用，因为如果 Moment 不知道你指定的语言环境，它就不会更改语言环境。

```javascript
moment.locale('fr'); // 'fr'
moment.locale('tq'); // 'fr'
```

也可以指定一个语言环境的列表，Moment 将会使用它具有本地化的第一个语言环境。

```javascript
moment.locale(['tq', 'fr']); // 'fr'
```

Moment 还将会尝试从最特定到最不特定的语言环境说明符子字符串，直到找到它知道的语言环境。
当为 Moment 提供从用户环境中拉出的语言环境字符串（例如 `window.navigator.language`）时，这很有用。

```javascript
moment.locale('en-NZ'); // 'en'
```

最后，Moment 将会通过一系列语言环境及其子字符串进行智能搜索。


```javascript
moment.locale(['en-NZ', 'en-AU']); // 'en-au', 而不是 'en'
```
