1. Для начала создается Файл Context.jsx. В ней создается контекст

```
import React, { createContext } from "react"
const Context = createContext()
export default Context
```

2.  Далее Потребуется обернуть всеь проект "Context.Provider value={...}", в значений value указываем данные для передачи в дочерние компоненты.

```
import Context from "./components/useContext/Context"

const [context, setContext] = useState(false)
return (
    Context.Provider value={[context && "coco", setContext]}>
        <ComponentA />
        <ComponentB />
        <ComponentC />
    <Context.Provider>
)
```

3.  ВСе компоненты обренутые в Context.Provider имеет доступ к самим данным контекста, что не приходится прокидывать через пропсы.

```
import React, { useContext } from "react"

const ComponentA = () => {
  const [context, setContext] = useContext(Context)
  return (
    <div>
      ComponentA :
      <button onClick={() => setContext(!context)}>{context}</button>
    </div>
  )
}
```
