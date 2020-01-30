---
title: moment(String) 多个格式
version: 1.0.0
signature: |
  moment(String, String[], String, Boolean);
---


如果不知道输入字符串的确切格式，但是知道它可能是多种格式之一，则可以使用格式数组。

这与[字符串 + 格式][parsing_string-format]相同，只是它将会尝试将输入匹配为多种格式。

```js
moment("12-25-1995", ["MM-DD-YYYY", "YYYY-MM-DD"]);
```

从 **2.3.0** 版本开始，Moment 使用一些简单的试探法来确定要使用的格式。
这是为了：

 * 优先使用能生成[有效][moment.isValid]日期（而不是无效日期）的格式。 
 * 优先使用能解析更多（而不是更少）字符串的格式，且优先使用解析更多（而不是更少）的格式，即优先更严格的解析。
 * 优先使用在数组中前面（而不是后面）的格式。

```js
moment("29-06-1995", ["MM-DD-YYYY", "DD-MM", "DD-MM-YYYY"]); // 使用最后一种格式。
moment("05-06-1995", ["MM-DD-YYYY", "DD-MM-YYYY"]);          // 使用第一种格式
```

还可以指定语言环境和严格性参数。
它们的工作方式与单一格式的情况相同。

```js
moment("29-06-1995", ["MM-DD-YYYY", "DD-MM-YYYY"], 'fr');       // 使用 'fr' 语言环境。
moment("29-06-1995", ["MM-DD-YYYY", "DD-MM-YYYY"], true);       // 使用严格的解析。
moment("05-06-1995", ["MM-DD-YYYY", "DD-MM-YYYY"], 'fr', true); // 使用 'fr' 语言环境和严格的解析。
```

注意：解析多种格式比解析单一格式要慢得多。
如果可以避免，则解析单一格式要快得多。

