### Событийный цикл

В Event Loop разделен на 3 блока, каждый блок выполняется с определенной последовательностью.

1. Основной поток
   - Функции, методы и т.д
2. МикроЗадачи
   - входят Promise, then, catch, async-await etc.
3. МакроЗадачи
   - Входят setTimeout, eventMouse etc.

- Также очередь в цикле работает по методу "первый пришел - первый вышел", т.е задачи будут выполнять сверху вниз последовательно.

---

Более подробный алгоритм событийного цикла (хоть и упрощённый в сравнении со спецификацией):

1. Выбрать и исполнить старейшую задачу из очереди макрозадач (например, «script»).
2. Исполнить все микрозадачи:
   - Пока очередь микрозадач не пуста: - Выбрать из очереди и исполнить старейшую микрозадачу
3. Отрисовать изменения страницы, если они есть.
4. Если очередь макрозадач пуста – подождать, пока появится макрозадача.
5. Перейти к шагу 1.
   Чтобы добавить в очередь новую макрозадачу:

- ![Event loop](https://images.velog.io/images/gtfo/post/03ef68fc-c4bc-4de0-993e-8415d21ed5a2/%E1%84%86%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%8F%E1%85%B3%E1%84%85%E1%85%A9%E1%84%90%E1%85%A2%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3.gif)
