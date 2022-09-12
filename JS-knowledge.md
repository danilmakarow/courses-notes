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

  #
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

Пять значений что будут значить в false, когда мы пытаемся преобразовать их boolean. 

`0, '', undefined, NaN, null` except of `falce` of course

<strong>JavaScript has dynamic typing: </strong>В JS в первых трёх типах нет необходимости обозначать тип данных в переменной, как в других языках. Он определяется сам. <strong>И тип данных хранит Само Значение, а не переменная. То есть бокс хранит значениe, что имеет тип данных</strong> Это значит, что можно без проблем менять тип данных в переменной.

Можно менять типы данных между собой - только первые три. Функции для этого - в отдельной вкладке. <strong>Type Coersion:</strong>Так же js меняет типы данных автоматически: для операторов, использующих цифры, как `* ** / -` преобразует тип в намбер. `console.log('23'-'10'*3);` при компиляции выдаст число, а не ошибку. А оператор `+` наоборот - с намберов делает стринги, что бы скомпилировать код и соеденить разные типы данных: `const jonas = "i'm " + 45 + "and another im " + 23;`. В другом языке нужно было бы писать ` + String(23);`, так как плюсование разных типов данных невозможно - будет ошибка. Но не в джаве. 

Классный пример, нужно угадать ответ: 
  
    let n = "1" + 1;
    n = n - 1;
    console.log(n);

  <details><summary>  answer </summary> 10 </details>
  
 #

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

`===` & `==` - приравнивают значения. Но тройной - строгий. Двойной - делает коррекцию типов. То есть двойной оператор покажет одно чилсло в двух видах - string & number равными, вернёт `true`. А строгий - вернёт `falce`, так как он не корректирует типы.

`!==` & `!=` - Такой же прикол как и свехру, только знак неравенства

  <strong>Лучше юзать строгий - так как с коррекцией полон тайн и загадок, и может быть причиной неожиданных багов. Негласное правило для чистоты кода.</strong>

##
  </details> 

<details> <summary>  and, or & not operators </summary> 

<img src="https://i.ibb.co/2PKDrXR/image.png" alt="image" width="65%">

Логика работы их с булеаном на картинке. Пример использования всех трех: 
  
    console.log(driversLicense && goodVision);
    console.log(driversLicense || goodVision);
    console.log(!goodVision);
  
##
  </details> 
  
  У разных операторов есть разный приоритет. Это обьясняет, почему в сравхениях двух примеров перед сравнением он считает эти примеры - у операторов сравнения низкий приоритет. Их список можно глянуть на mdn. Так же у разных операторов разный порядок начала считывания - с левой стороны примера или правой. Мб пригодится в дебагинге.
  
  Другие операторы:

`typeof` - выдаёт тип данных переменной или текста после оператора. ! багует при попытке определить тип значения null.
  
#
</details> 

<details> <summary>  Не большие разделы </summary> 
  
<details> <summary>  Template literals </summary> 
  С ES6 новый путь вывода strings вместе с переменными. Как было раньше: 
  
  
    const jonas =
    "i'm " + firstName + ", a " + (now - birthYear) + " years old " + job + "!";

  А вот новый путь

    const jonasNew = `I'm ${firstName}, a ${now - birthYear} years old ${job}!`;
  
  То есть для вставки переменных и кода не нужно использовать операторы. Ахуенно! Так же для пепреноса на другую строку достаточно перенести на другую строку в коде, операторы не нужны
  
 I'm Jonas, a 46 years old teacher!
  
##

  </details> 
  
<details> <summary>  IF ELSE </summary> 
  
  Состоит из блоков кода.  И любая переменная, которую мы объявляем внутри одного из этих блоков не будет доступа снаружи блока.
  
    if (оцентиаветься) {
    Если положительное - этот код испольняется
    } else {
    если falce в оценке - этот
    }

  Так же можно писать действие без скобок - если оно не большое, в одну строку с функцией
  
    if (age === 18) console.log("YAY");

  Есть ещё разширенная функция - `else if` - идёт после иф перед елсе. Создаёт дополнительное условие, их может быть неограниченное количество

  ##
  </details> 

<details> <summary> SWITCH </summary> 

`switch` заменяет иф елсе, если нужно в зависимости от разных значений одной переменной выдадть разный результат. То есть тут только одна переменная проверяется. Вот пример:  

    switch (day) {
     case "monday": // day === 'monday'
       console.log("plan course structure");
        console.log("go to coding meetup");
        break;
     case "tuesday":
       console.log("prepare videos");
        break;
     case "wednesday":
      case "thursday":
       console.log("write code exapmles");
       break;
     case "friday":
      console.log("record videos");
      break;
    case "saturday":
    case "sunday":
       console.log("Enjoy the weekend :D");
       break;
    default:
      console.log("not a valid day");
   }

Тут после кейса указываем значение, и после код который он выполнит. После закрыть этот блок кода - бреак, и в конце `default`- в случаэ если все кейсы получат false. Простая и удобная функция



 ##
  </details> 
  
#
  </details> 

<details> <summary>  Функции </summary>  

  Делают какую-либо функцию
  
Переоброзование String to Number: `console.log(Number(inputYear));` Если приобразовать не цифры - выдаст NaN - Not a Number.(Технически это неправильная цифра)
  
  В обратно направлении тоже работает: `console.log(String(23));` <string>Важно: необходимо писать с большой буквы, иначе не сработает.</string>

  #
  
  </details> 
