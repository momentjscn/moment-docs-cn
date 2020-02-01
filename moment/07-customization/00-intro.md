---
title: 自定义
---

Moment.js 非常容易自定义。
通常，应该使用自定义创建语言环境。

```javascript
moment.locale('en-my-settings', {
    // 自定义
});
```

可以通过传入 `null` 作为第二个参数来移除先前定义的语言环境。
删除的语言环境将不再可用。

```javascript
moment.locale('fr'); // 'fr'
moment.locale('en'); // 'en'
moment.locale('fr', null);
moment.locale('fr'); // 'en'
```

从 **2.12.0** 开始，可以创建从父语言环境继承的语言环境。

```javascript
moment.defineLocale('en-foo', {
  parentLocale: 'en',
  /* */
});
```

在语言环境中未指定的属性将会从父语言环境中继承。

从 **2.16.0** 版本开始，可以使用尚未定义或加载的父语言环境来定义语言环境。

```javascript
moment.defineLocale('fakeLocale', {parentLocale:'xyz'})
```

从 **2.21.0** 开始，当尝试使用新定义的语言环境创建 moment 时，如果存在父语言环境，则 moment 将会尝试延迟加载它。
当失败时，它会默认将父语言环境设置为全局的语言环境。

从 **2.12.0** 开始，还可以更新语言环境的属性。

```javascript
moment.updateLocale('en', {
  /**/
});
```

指定的任何属性将会被更新，而其他属性将会保持不变。
此函数不会影响已经存在的 moment。

要还原更新，则使用：

```javascript
moment.updateLocale('en', null);
```

使用 ``moment.locale()`` 更改现有的语言环境已废弃于 **2.12.0**。
改用 ``moment.updateLocale()``。
