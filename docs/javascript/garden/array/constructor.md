# Конструктор Array

Так как в конструкторе `Array` есть некоторая двусмысленность, касающаяся его параметров, настоятельно рекомендуется при создании массивов всегда использовать синтаксис литеральной нотации — `[]`.

```js
;[1, 2, 3] // Результат: [1, 2, 3]
new Array(1, 2, 3) // Результат: [1, 2, 3]
;[3] // Результат: [3]
new Array(3) // Результат: []
new Array('3') // Результат: ['3']
```

В случае, когда в конструктор `Array` передаётся один аргумент и этот аргумент имеет тип `Number`, конструктор возвращает новый, _заполненный случайными значениями_, массив, имеющий длину равную значению переданного аргумента. Стоит заметить, что в этом случае будет установлено только свойство `length` нового массива, индексы массива фактически не будут проинициализированы.

```js
var arr = new Array(3)
arr[1] // не определён, undefined
1 in arr // false, индекс не был установлен
```

Поведение, которое позволяет изначально установить только размер массива, может пригодиться лишь в нескольких случаях, таких как повторение строк, за счёт чего избегается использование цикла `for`.

```js
new Array(count + 1).join(stringToRepeat)
```

## Заключение

Использование конструктора `Array` нужно избегать, насколько это возможно. Литералы определённо предпочтительнее — это краткая запись и она имеет более понятный синтаксис, так что при этом даже улучшается читабельность кода.