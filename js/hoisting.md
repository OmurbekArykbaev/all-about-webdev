### Hoisting или же всплытие

🔵 Все декларирования всплывают `const, let, var, class`

:x: Но иницализация не работает с `let, const`, если вызвать переменные до их объявления появится ошибка.

⭐ В процессе обьявлений переменной через `var`, в режиме `runtime` происходит всплытие т.е переменные в самом начале кода объявляются далее заначения присваиваются указанной строке кода пример:

```
console.log(number) // undefind

var number = 101

console.log(number) // 101
```

❗ что происходит в рантайме:

```
var number

console.log(number) // undefind

number = 101

console.log(number) // 101
```
