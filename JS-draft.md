<!-- 
<details> <summary>  HTML </summary>  </details> 
-->
# Summary from JavaScript course

<details> <summary>генерал драфтс</summary>  
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
TDZ - Temporal dead zone. Зона, в которой джс уже знает о существовании переменной, но вызвать её нельзя. Эта зона начинаеться с начала скоупа(блока кода) до момента обьявления переменной. Это для избежания багов и корректной работы const. Если вар можно вызвать до инициализации - он выдаст undifined, что супер странно и может привести к сложным багам. Ведь перед началом выполнения кода идёт скан на все переменные, это и позволяет использовать декларирующие функции до их обьявления. Лет и конст это пофиксили. И как конст может быть неизменной, если бы его значение менялось с undifined на обьявленное. Вместо этого они имеют <`unіnitializated`> и выдают ошибку при попытке вызова.
 </details> 

