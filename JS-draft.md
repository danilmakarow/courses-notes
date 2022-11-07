<!-- 
<details> <summary>  HTML </summary>  </details> 
-->
# Summary from JavaScript course

<details> <summary>генерал драфтс</summary>  
Классный пример как подходить к разработке аппа, исходя из нарисовки функционала

<img src="https://i.ibb.co/89smpkp/image.png" alt="image" border="0">

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



