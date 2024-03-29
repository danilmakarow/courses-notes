<!-- 

<details><summary>HTML</summary>
##
</details> 

-->
# Summary from JavaScript course

<details><summary>генерал драфтс</summary>  
Классный пример как подходить к разработке аппа, исходя из нарисовки функционала

<img src="https://i.ibb.co/89smpkp/image.png" alt="image" border="0">

По движку JS

Runtime is just like a box that contains all the JavaScript related stuff that we need.

<strong>AST</strong> - abstract syntax tree.

</details>   

<details> <summary>  DOM </summary> 

## Document Object Model
  
В двух словах - API позвoляющая джс взаимодействовать с HTML & CSS.

    document.querySelector('.check').addEventListener('click', function () {
      document.querySelector('.modal').classList.add('hidden');
    });

Где `document` - object, `querySelector` `addEventListener` `classList` - methods. Методы:

`querySelector` `querySelectorAll` - внутрь в формате `('.modal')` прописываеться клас/ид обьекта. querySelectorAll выделяет все обьекты по запросу. querySelector - только первый в коде

`btnsModal[i].addEventListener('click', function () {});` - добавляет к ожиданию клика на елемент, в последствии обращается к функции, что стоит вторым аргументом. функция обязательно должна быть Expression.

</details> 

<details> <summary>  Теория </summary>
Про JS  в двух словах: 

Когда код запускаеться, с самого начала идет `Parsing`(Abstract system tree) - разбитие кода на своеобразное дерево. После код проходит `Compilation` - перевод в машинный 01 и после `Execution` - выполнение. Когда код переделан в машинный и собирается компилиться - для него создается среда, названная  `Global execution context` Где компилиться вес кодь верхнего уровня - без функций. С них он берет только их названия, что бы их можно было вызвать в будущем. 

Вот это вся концепция - называется `Call stack`. `Execution` Происходит в три этапа: создания глобального контекста. Его инициализация. И потом инициализация функций и ожидания Callback - ивентов.

Как происходит выполнение кода: для начала общая среда, что хранит в себе все кроме функций и выполняет. И по мере как в последней строке используется обращение к функции, call stack создает для нее новую среду и помещает наверх себя. (и все что декларируется внутри этой среды записывается в ee Variable Environment, а не в общий. По этому к ним нет доступа)  То, что верхнее - будет выполняться первее.
  
JS использует `Just-in-time` (JIT) compilation: Entire code is converted into machine code at once, then executed immediately.
    
Про JS Engine в двух словах: 

JS Engine состоит из `Call Stack` & `Heap`.  `Heap`  - сборка мусора - хранилище ссылочных типов данных. и `Call Stack` - как to do list, хранит задачи к выполнению. Когда в коде каким-либо образом(по ивенту или нет) инициируеться функция - для нее создаеться среда - `execution context`. Он есть один - глобальный и остальные - создаються функциями. Как to do list - когда идет ображение к функции и создается среда - она помещается наверх стэка. Выполняеться только самая верхняя, все что ниже - на паузе. По этому JS может выполнять только один процесс, не многопоточен. Когда весь код выполнен в стеке будет только глобальная среда, до тех пор пока не затушиться вкладка.

`execution context` имеет 3 состовляющих: variable invironment, scope chain & this keyword. 


<details><summary>variable invironment</summary>

Хранит в себе всё задекларированное в текущей функции и обьект с аргументами. Так же имеет механизм Hoisting.

`Hoisting` - подьем, делает некоторые типы переменных доступными ещё до декларирования. Просто перед выполнением кода идёт скан на обьявление переменных. Это происходит на первом этапе в Execution - creation of global execution context. (94 ст. лекции)

С какими типами переменных работает:
`Function declaration`: Полностью нормально работает, вызываема до обьявления
`var variables`: Можно вызвать до обьявления, но будет иметь Undifined. Говно.
`let & const variables`: Нельзя, вызывать только после обьявления. Они в TDZ - их нельзя вызвать между Scope и их обьявлением. (Scope - хранит все обьявленные переменные в самом начале кода)
Funcion expression & arrow: хранятся в переменных, поэтому зависит от того, как они были обявлены.

Все декларации и переменные сканируются до выполнения кода, по этому технически js знает о их существовании до обьявления в коде. Но лет и конст - имеют Temporal dead zone - это все что находиться в блоке/функции до их обявления, где язык знает что они есть, но вызвать нельзя. TDZ - существует для того что бы ловить ошибки о попытке инициализировать переменную до обявления.

##
</details> 


`Scope Chain` - Цепь ссылок. Каждая функция и блок кода имеют свой Scope, что хранит все доступные переменные для этого scope, что пренадлежит `execution context`.

<details><summary>This</summary>
кейворд, что при вызове в методе вернёт название обьекта. И по этому можно копировать метод, не ломав логику. 
<img src="https://i.ibb.co/YDpZFMR/image.png" alt="image" border="0">

Так же можно совмещать с стрелочными функциями в методе, так как они используют this of parent scope, что в этом случае будет this метода, что тоже будет работать

##
</details> 


##
 </details> 



<details><summary>Data Structures</summary>
  
##

Деструктуризация - робота с данными - примитивными и ссылочными.

<details><summary>Destructuing Arrays & Objects</summary>
  
Начнем с массивов.
  
    const profile = ["Oluwatobi", "Sofela", "codesweetly.com"];
    const [firstName, lastName, website] = profile;

Тут было создано 3 переменных, хранящих три елемента массива. Если нужно пропустить один елемент в массиве: `[firstName, , lastName, website] = profile;`. так же можно массивы внутри массивов: `const [starter, [main, test]] = restaurant.order;`. И придавать им дефолтное значение: `const [h = 1, k = 1, l = 1] = [2, 4];`. Вывод будет выглядеть: `2 4 1`. 

Дальше обьекты.

    let a = 22;
    let b = 66;
    const obj = {
      a: 12,
      b: 55
    };
    ({ a, b } = obj);

Для деструктуризации обьекта нужно что бы переменные были названы как свойства в нем. Это фикситься позже. Если нужно сделать любую деструктуризацитю с уже существующими переменными - нужно завести в скобки`()`, иначе ошибка. Фиксим неудобство с названиями: 
  
    const {
      name: restName = "name",
      openingHours: hours,
      categories: tags,
      secondMenu: menu = "no second menu",
      thirdMenu
    } = restaurant;

Где то что до двоеточия - свойство, после - переменная и = дефаултное значение. Дефаултное значение будет применяться если свойства в обьекте нет. Если в обьекте нет свойства и не указано дефаулт - переменная будет undifined. Вложенные обьекты: 
![image](https://user-images.githubusercontent.com/105916992/206476384-1f0d6806-4aa0-4f05-be60-e5b2b23c77df.png)

    const {
     sat: { open: openSat, close: closeSat }
    } = openingHours;

Где будет созданы две переменных: `openSat` & `closeSat` с значениями 0 24, как в обьекте. То есть вместо названия после двоеточия открываеться новая деструктуризация, где обьявлены, названы и даны значения двум переменным.
  
##
</details> 

<details><summary>Spread Opertor, Rest pattern & Parametrs</summary>
 
### Spread Operator  
  
    const newArr = [1, 2, ...arr];

Оператор `...Array` - возвращает все значения массива через кому. С правой части от =. Просто раскрывает массив. подходит для использования там, где ожидаються данные через кому. Как для аргумента. Так же работает с стрингами - возвращает все символы стринга по одному через кому.

### Rest Pattern  & Parameter

Остаточный параметр. It will take the rest of the elements. Берет данные через кому и делает массив. Собирает неприсвоенные значения в диструктуризации массива, должен быть последним елементом деструктуризации. 
  
    const[, Pizza, , Risotto, ...otherFood] = [...restaurant.mainMenu, ...restaurant.starterMenu];
  
Cоберет 1, 3 елемент массива в переменные, а все остальные пойдут в массив `otherFood`. Работает и с обьектами.  

    const {sat:weekEnd, ...weekDays} = restaurant.openingHours; 

Заберет sat свойство в переменную `weekEnd`, а все остальные свойства уйдут в `weekDays` обьект. 

Rest Arguments. Использование в функции для аргумента, если аргумент - массив. Можно вызывать не массивом, а просто данными через кому. А в обьявлении функции как входящий аргумент прописать `const add = function(...arr){`. Тогда входящие данные будут сформированы в массив функцией тут, для дальнейшего использования.

В общем, Spread operator сотит использовать  где место для Значений через кому, а Rest Pattern где место для переменных через кому.

##
</details> 

<details><summary>Optional Chain Operator</summary>

`?.` Проверяет есть ли свойство, если нет - сразу вернет undefined, избежавши ошабку. Проверяет по методу Nullish - только Undefined and Null дадут фолс. 0 и "" - пройдут.

    console.log(restaurant.openingHours.mon?.open);
    console.log(restaurant.openingHours?.fri?.open);

Это на свойствах. На методах также, после его названия и перед агрументом:

    console.log(restaurant.order?.(2, 2));
    console.log(restaurant.orderPizzas?.(2, 2)) ?? 'Method doesnt exist';

На втором примере - скомбинировано с дефолтным значением с помощью оператора нулевого слияния (Nullish Coalescing Operator). Если метода не зуществует будет выведена строка в консоль. Так же работает с обьектами в массивах:

    const users = [{ name: 'Jonas', email: 'dknvdk@danil.io' }];
    console.log(users[0]?.name ?? 'Array empty');

Проверяет есть ли свойство в елементе массива. Если нет выведет сообщение.

##
</details> 

<details><summary>Strings</summary>

У стрингов просто куча методов. Так же они являются итераторами. От части робота с ними похожа на роботу з массивами.

Вообще стринг - не ссылочный тип данных. Но при использовании на нем методов джс автоматом трансформирует его в Обьект стринг - свою структуру данных для роботы с стрингами. `new String('Glory to Ukraine');`Это можно сделать и в ручную, выглядит примерно так. typeof на этой структуре данных вернет обьект.  Пойдем по операторам::

С ними работает деструктуризация: `[...plane]` & `[...'Ukranian Airlines']`. Можно вытащить id елемента, как в массиве:`plane[2]` & `'B737'[2]`. `airLine.length` & `'Air Lines'.length` вернет их длину. Дальше по методам:

`airLine.indexOf('n')` - индекс первой искаемой буквы. `airLine.lastIndexOf('n')` то же самое, но последней. Работает и с словами. `airLine.slice(4)` - обрезает по указанным индексам. Имеет два параметра, первый - старт, второй - конец. Если без второго, то обрежет с старата до конца стринга. Второй параметр обрезает НЕ ВКЛЮЧИТЕЛЬНО. То есть `airLine.slice(9, 12)` вернет 3 символа - 9, 10, 11. Так же можно задавать минусовые - они начинают отсчет с конца.

`let priceUS = priceGB.replace('₴', '$')` Заменяет первый параметр на второй. Но только первый попавшийся. `replaceAll`заменяет все. Методы с булианами, тут все очевидно: 

    plane.includes('A328');
    plane.startsWith('A32');
    plane.endsWith('neo');

Другие методы:

    passenger.toLowerCase();
    passenger.toUpperCase();
    loginEmail.trim(); // обрезает энтеры и лишние пробелы в до и после текста.
    message2.repeat(5);
    message.padStart(25, '+').padEnd(35, '-') // добавляют указаных знаков до указанной длины стринга.
    name.split(' '); // вернет массив с разделеным стрингом по указанному елементу.
    readyName.join(' '); //соеденит елементы массива через указанный стринг. 

Пример их комбинации: Принимает через ентр текст_в_таком_формате, а возвращаетВотТаком.

    document.querySelector('button').addEventListener('click', function () {
     console.clear();
     const text = document.querySelector('textarea').value;
     document.querySelector('textarea').value = '';
     let success = 1;

     for (let string of text.split('\n')) {
       string = string.toLowerCase().trim();
       let camel = [];
        for (const word of string.split('_'))
          camel.push(word.replace(word[0], word[0].toUpperCase()));

        camel[0] = camel[0].replace(camel[0][0], camel[0][0].toLowerCase());
        console.log(camel.join('').padEnd(25, ' ') + '✅'.repeat(success));
       success++;
     }
    });


##
</details> 

<details><summary>Sets & Maps</summary>
Структуры данных. 

### maps methods: has, get, set, delete, clear, size

    const gameEvents = new Map([
      [17, '⚽️ GOAL'],
      [36, '🔁 Substitution'],
      [47, '⚽️ GOAL']
    ]); // обозначать свойства можно так

    rest.set('name', 'Classiko Italiano'); // или так

    console.log([...question]); // деструктуризация работает, и стандартные методы:
    console.log([...question.entries()]);
    console.log([...question.keys()]);
    console.log([...question.values()]);
    rest.get(time > rest.get('open') && time < rest.get('close'))
    rest.has('categories')
    gameEvents.delete(64) // делитит по кею

### Sets

collection of unique values

Принимает итераторы. Обьявление:

    const ordersSet = new Set([
      'Pasta',
      'Pizza',
      'Pizza',
      'Risotto',
    ]);

Методы: size, has, add, delete, clear


##
</details> 

##
</details> 
