## Асинхроность

Асинхроность - это коротко о том когда будет выполнена определенная задача, она может быть выполнена через 2сек или через 1 минуту, это неизвестно.

- Таймеры не блокируют интерпритацию, т.е выполнение кода в рантайме, он кладет задачу в очередь.

- Есть очередь в Event Loop, все таймеры поступают туда, далее по истичению времени в указанном таймере будет выполнен, но только после после завершение всего "стека вызова".

- Контекст исполнения или основной поток кода является весь тот код который указан в скрипте

- Очередь вызова не начнет выполнятся пока, весь код который находиться в основном потоке не будет выполнен полностью.

---