## Хук useReducer это маленький аналог библиотеки Redux

Если в компоненте требуется менять большое количество данных, рекомендуется использовать useReducer нежели обычные хуки useState.

Пример:

1. Прежде всего нужно импортировать хук с нативного Реакта.

`import {useReducer} from "react"`

---

2. Далее давай создадим главную функцию reducer который будет работать с изменениями данных (мутировать данные).
   Присутствует два аргумента state и action.
   State - Первоначально идет присваивание initialState,далее сами данные которые берутся с UI, далее его мутация зависимо от action.type.
   Action - принимает два поля payload и type, в payload указывается любые данные которые приходят от пользователя,
   в type соответственно тип изминений (важно давать названия более краткие и понятные).

```
function reducer(state, action) {
--switch (action.type) {
--case "incr":
---return { count: state.count + 1 }
--case "decr":
---return { count: state.count - 1 }
--case "addText":
---return { text: action.payload }
--default:
---throw new Error("Action type was not found")
-}
}
```

---

3. Создаем первоначальную иницализирующую переменную initialState которую в итоге передадим в useReducer.

`const initialState = {count:0, text:"First word"}`

---

4. Далее деструктурируем переменные из useReducer, в аргументы Хука передаем нашу функцию reducer и initialStatе - для определения первоначального состояния state.

`const [state,dispatch] = useReducer(reducer, initialState)`

---

5. Можем использовать его в компоненте.

```
 <button onClick={() => dispatch({ type: "incr" })}>INCR +</button>
 <button onClick={() => dispatch({ type: "decr" })}>DECR -</button>
 <input type="text" value={state.text} onChange={(e) => dispatch({ type: "addText", payload: e.target.value })} />
```
