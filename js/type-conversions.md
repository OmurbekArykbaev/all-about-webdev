### Преоброзование типов

Существует 3 наиболее широко используемых преобразования: строковое, численное и логическое.

⭐ Логическое

Для примитивных значений работает очевидным образом. `String(value)`, выведет значение виде строки.

⭐ Числовое

```
let string = "123"
Number(string) // 123
Number(undefined) // NaN
Number(true / false) // 1 / 0
Number(" 123 ") // 123
Number("123z") // NaN
```

⭐ Логическое

```
0, null, undefined,  NaN, "" // false
```

Любое другое значение равно `true`
