<!-- 
<details> <summary>  HTML </summary>  </details> 
-->

# JavaScript Fundamentals 
###  Черновик с курса The Complete JavaScript Course 2022: From Zero to Expert! 

<details> <summary>  переменные </summary> 

  Обьявление переменной. Есть несколько операторов для этого: 
  
  `let` -  создание переменной с возможностью изменить в будщем. <strong>Can be mutated. </strong>
  
  `const` - создание переменной без возможности давать новое значение. <strong>Immutable variable.</strong>
  
  `var` - полностью как let
  
  <strong>Как их использовать?</strong> Для чистоты кода: обычно const, и let только когда уверены, что её нужно будет менять. Например: год рождения - конст, возраст - лет. Одно - не меняется, второе - да.
  
`let & const` - с обновления ES6, so they are modern JavaScript. const нельзя давать undefined. `var`- старый вариант обьявление переменных, лучше его избегать.
  
 Пример обьявления переменной
  
    let fistname='Jonas';

  
</details> 

<details> <summary>  types of data </summary> 
  
Есть два вида значений - обьекты и примитивные, все остальные.
  
Примитивные:
  
<strong>`Number`</strong> -Число с плавающей точкой. 23 = 23.0 в js.

<strong>`String`</strong> - просто текст.

<strong>`Boolean`</strong> - логический вид, принимает True/False

`Undefined` - Обьявленная переменная без значения, но позже может получить его.

`Null` - Обьявленная переменная но без значения, и дать значение ей его нельзя.

`Symbo` (ES2015)- Переменная с значением, что нельзя изменить. Подробности будут в конце курса.

`BigInt` (ES2020) - Может хранить огромные целые числа.

<strong>JavaScript has dynamic typing: </strong>В JS в первых трёх типах нет необходимости обозначать тип данных в переменной, как в других языках. Он определяется сам. <strong>И тип данных хранит Само Значение, а не переменная. То есть бокс хранит значениe, что имеет тип данных</strong> Это значит, что можно без проблем менять тип данных в переменной.

</details> 

<details> <summary>  операторы </summary> 
  
So an <strong>operator</strong> basically allows us to transform values or combine multiple values and really do all kinds of work with values. Есть много видов операторов, по порядку:
<details> <summary>  mathematical or arihmetic operators </summary> 
  
`+` `-` `/` `*` - очевидные операторы. `console.log(ageJonas * 2, ageJonas / 10);`

`**` - возвести в степень. `2 ** 3;` = 8

`+=` `-=` `*=` `/=`- операция к текущему значению. Пример: `x *= 10;` равно `x = x * 10;`
  
 `++` `--` - Прибавляет/отнимает к текущему значению 1. Example: `x++;` равно `x=x+1;`
  
 Операторы сравнения

`>` `<` `>=` `<=` - сравнивают значения, и возвращают результат в типе boolean. Example: `console.log(200>100)` return: `true`.

  </details> 
  
  Другие операторы:

`typeof` - выдаёт тип данных переменной или текста после оператора. ! багует при попытке определить тип значения null.
  
</details> 


