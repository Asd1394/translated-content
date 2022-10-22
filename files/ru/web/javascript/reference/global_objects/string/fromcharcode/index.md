---
title: String.fromCharCode()
slug: Web/JavaScript/Reference/Global_Objects/String/fromCharCode
tags:
  - JavaScript
  - Method
  - Reference
  - String
  - Unicode
translation_of: Web/JavaScript/Reference/Global_Objects/String/fromCharCode
---
{{JSRef("Global_Objects", "String")}}

## Сводка

Статический метод **`String.fromCharCode()`** возвращает строку, созданную из указанной последовательности значений единиц кода UTF-16.

.

## Синтаксис

```
String.fromCharCode(num1[, ...[, numN]])
```

### Параметры

- `num1, ..., numN`
  - : Последовательность чисел, являющихся значениями единиц кода UTF-16. Диапазон составляет от 0 до 65535 (0xFFFF). Числа больше 0xFFFF усекаются. Проверка достоверности не производится.

## Описание

Этот метод возвращает примитивную строку, а не объект {{jsxref("Global_Objects/String", "String")}}.

Поскольку метод `fromCharCode()` является статическим методом объекта {{jsxref("Global_Objects/String", "String")}}, вы всегда должны использовать его как `String.fromCharCode()`, а не как метод созданного вами экземпляра {{jsxref("Global_Objects/String", "String")}}.

## Примеры

### Пример: использование метода `fromCharCode()`

Следующий пример вернёт строку "ABC".

```js
String.fromCharCode(65, 66, 67);  // "ABC"
```

[Полная таблица UTF-16](https://asecuritysite.com/coding/asc2)

## Как заставить его работать с большими значениями

Хотя большинство распространённых значений Юникода может быть представлено одним 16-битным числом (как ожидалось на ранней стадии стандартизации JavaScript) и метод `fromCharCode()` может использоваться для возврата одного символа для самых распространённых значений (точнее, значений UCS-2, которые являются подмножеством самых распространённых символов UTF-16), для работы со ВСЕМИ допустимыми значениями Юникода (занимающими до 21 бита) одного метода `fromCharCode()` недостаточно. Поскольку большие кодовые точки используют (самое меньшее) два «суррогатных» числа для представления одного символа, для возврата таких пар можно использовать метод {{jsxref("String.fromCodePoint()")}} (являющийся частью черновика ES6) и, таким образом, адекватно представлять эти символы.

## Спецификации

{{Specifications}}

## Совместимость с браузерами

{{Compat}}

## Смотрите также

- {{jsxref("String.fromCodePoint()")}}
- {{jsxref("String.prototype.charAt()")}}
- {{jsxref("String.prototype.charCodeAt()")}}
- {{jsxref("String.prototype.codePointAt()")}}