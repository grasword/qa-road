# Interview questions

### 1) What is the difference between a statement and an expression in JS?&#x20;

Javascript program consists of statements. They are executed one by one, in the same order as they are written. Statements can contain other constructions like expressions, keywords, operators, and other stuff.

For example this is **statements**:

```javascript
let declaredVariable; // variable declaration is a statement
let otherVariable = 0; // even with assignment
function functionCall() { // function declaration is a statement
}
if(true){} // if is statement
2+2; // even this is statement
// Even though it consists from only one expression
```

**Expressions** are parts of statements that return values. So expressions can be used whenever value is expected.

And this is expressions:&#x20;

```javascript
2+2
true
true && false
functionCall() // whatever the function returns
declaredVariable // whatever the variable value was
declaredVariable = 'new value' // assignment is an expression
```

Actually just `"foo"`, `{foo: 'bar'}`, `[1,2,3]`, or `42` are also expressions, they are called `literals` (string, object, array and number literal) because they just return their literal value.

And even this small expressions can be statements on their own.

```javascript
2;
```

This is statement. It’s useless. It doesn’t help, but still. As you can see it consists from only one expression. Statements like this are called `expression statements`.

Sometimes you can use `expression-statements` instead of usual statements, `if-else` is a good example:

```javascript
let foo;
if (bar === 'bazz') {
  foo = bar;
} else {
  foo = null;
}
```

You can use this `expression` instead:

```javascript
let foo = bar === 'bazz' ? bar : null
```

Source: [https://maksimivanov.com/posts/statements-expressions-js/](https://maksimivanov.com/posts/statements-expressions-js/)

### 2) What’s the difference between JavaScript primitive values and objects?&#x20;

JavaScript currently supports eight data types. All of these data types (`Booleans`, `Null`, `Undefined`, `Number`, `BigInt`, `String`, `Symbol`) are **primitive values** except for **object references**.

`Arrays`, `functions`, and `Dates` all play an important role in JavaScript programs, but they are really just objects under the hood.

Primitive values can be stored in variables directly. Objects, on the other hand, are stored as references. A variable that has been assigned an object does not store that object directly, it stores the memory address of the location that the object exists at.

#### The Difference Between a Value and a Reference <a href="#f877" id="f877"></a>

Primitive values and object references are stored in JavaScript programs in different ways.

When a primitive value is assigned to a variable (eg `let foo = ‘bar’`), the variable is set to that **value** directly.

When the variable is assigned with an object, however, things are different. Instead of containing the value directly, that variable contains a **reference** to it.

#### The Difference Between Immutable and Mutable Data <a href="#dcb9" id="dcb9"></a>

One key difference between primitive values and object references is **mutability**. Primitive values are **immutable** and object references are **mutable**.

The reason primitive types are immutable is that primitives have no methods attached, which means there is no possible way to mutate the string in the first place. A primitive has a value and no properties.

// Source: [https://betterprogramming.pub/intermediate-javascript-whats-the-difference-between-primitive-values-and-object-references-e863d70677b](https://betterprogramming.pub/intermediate-javascript-whats-the-difference-between-primitive-values-and-object-references-e863d70677b)

### 3) What do people mean when they say “everything” is an object in JS?&#x20;

The answer is a little bit of JavaScript magic involving wrapper-objects and autoboxing. When a method like `string.length` is called on a primitive type like a string, JavaScript initiates an action called _autoboxing_.

Autoboxing is the process by which JavaScript wraps a primitive in an object, but only temporarily.

`String` is a global function that creates a primitive string when passed in an argument, but you can also use the `String` function as a constructor function. And this will create a new object (often referred to as _wrapper object_) representing the string `"dog"`, with the following properties:

```
const pet = new String("dog"){  0: "d",  1: "o",  2: "g",  length: 3 }
```

When `.length` is called on a primitive string, the JavaScript engine converts the string to a `String` object as shown above. It is then mutable, and you gain access to the many built-in methods attached to `String`. Once the method has been resolved, the above wrapper object is discarded. The same applies to numbers and Booleans (it does not apply to null and undefined).

Here’s a breakdown of the work JavaScript does under the hood:

1. Create a `String` wrapper object, equivalent to using `new String()`.
2. Call the inherited `.length` method on the `String` wrapper object.
3. Once the method is complete, the wrapper `String` object is discarded.
4. Return the mutated primitive string (if a method like `substr( )` is used).

#### Is Everything in JavaScript an Object? <a href="#78d8" id="78d8"></a>

Not quite. It might be more accurate to say something along the lines of everything in JavaScript can appear to behave like an object. __ Primitives like `String`, `boolean`, and `number` can behave like objects thanks to JavaScript features called object-wrapping and autoboxing.

// Source: [https://betterprogramming.pub/everything-in-javascript-is-an-object-except-for-when-it-isnt-305bc65a3410](https://betterprogramming.pub/everything-in-javascript-is-an-object-except-for-when-it-isnt-305bc65a3410)

### 4) What is not an object in JS?&#x20;

**Primitive values** are not objects(`Booleans`, `Null`, `Undefined`, `Number`, `BigInt`, `String`, `Symbol`)  &#x20;

### 5) In what ways are primitive values objects or not?&#x20;

Primitives like `String`, `boolean`, and `number` can behave like objects thanks to JavaScript features called object-wrapping and autoboxing.

### 6) How is a function an object? What about an array? What are the exact definitions of a variable, a declaration, and an assignment?

#### How is a function an object?&#x20;

In JavaScript, functions are first-class objects, because they can have properties and methods just like any other object. What distinguishes them from other objects is that functions can be called. In brief, they are [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function) objects.

// Source: [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions)

#### What about an array?

The JavaScript **`Array`** class is a global object that is used in the construction of arrays; which are high-level, list-like objects.

// Source: [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array)

#### What are the exact definitions of a variable?

Variable - In computer programming, a **variable** or **scalar** is an abstract storage location paired with an associated symbolic name, which contains some known or unknown quantity of information referred to as a _value_; or in simpler terms, a variable is a container for a particular set of bits or type of data (like integer, float, String etc...). A variable can eventually be associated with or identified by a memory address. The variable name is the usual way to reference the stored value, in addition to referring to the variable itself, depending on the context. This separation of name and content allows the name to be used independently of the exact information it represents. The identifier in computer source code can be bound to a value during run time, and the value of the variable may thus change during the course of program execution.\
// Source: [https://en.wikipedia.org/wiki/Variable\_(computer\_science)](https://en.wikipedia.org/wiki/Variable\_\(computer\_science\))

#### What are the exact definitions of a declaration?

In computer programming, a **declaration** is a language construct that specifies properties of an identifier: it declares what a word (identifier) "means". Declarations are most commonly used for functions, variables, constants, and classes, but can also be used for other entities such as enumerations and type definitions. Beyond the name (the identifier itself) and the kind of entity (function, variable, etc.), declarations typically specify the data type (for variables and constants), or the type signature (for functions); types may also include dimensions, such as for arrays. A declaration is used to announce the existence of the entity to the compiler; this is important in those strongly typed languages that require functions, variables, and constants, and their types to be specified with a declaration before use, and is used in forward declaration.

// Source:  [https://en.wikipedia.org/wiki/Declaration\_(computer\_programming)](https://en.wikipedia.org/wiki/Declaration\_\(computer\_programming\))

#### What are the exact definitions of a an assignment?

The simple assignment operator (`=`) is used to assign a value to a variable. The assignment operation evaluates to the assigned value.

// Source: [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Assignment](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Assignment)

### 7) What is control flow?&#x20;

The _control flow_ is the order in which the computer executes statements in a script.

Code is run in order from the first line in the file to the last line, unless the computer runs across the (extremely frequent) structures that change the control flow, such as conditionals and loops.

Source: [https://developer.mozilla.org/en-US/docs/Glossary/Control\_flow](https://developer.mozilla.org/en-US/docs/Glossary/Control\_flow)

### 8) What is the difference between `===` and `==`?

The loose equality operator (`==`) will return `true` if the values of the two items being compared are the same. The strict equality operator (`===`) returns `true` if the values **and** types of the two objects being compared are the same.



### 9)What is the hoisting?

Sourse: [https://developer.mozilla.org/ru/docs/Glossary/Hoisting](https://developer.mozilla.org/ru/docs/Glossary/Hoisting)

Поднятие (hoisting) — термин, который вы _не_ встретите в документации JavaScript. Поднятие задумывалось как общий способ мышления о том, как контекст исполнения (в частности, фазы создания и исполнения) работает в JavaScript. Однако, hoisting может привести и к недоразумениям. Например, hoisting учит, что объявление переменной или функции физически перемещается в начало вашего кода, хотя в действительности этого не происходит. На самом же деле, объявления переменных и функций попадают в память в процессе фазы компиляции, но остаются в коде на том месте, где вы их объявили.

### 10) [What is the DOM?](https://developer.mozilla.org/en-US/docs/Web/API/Document\_Object\_Model/Introduction#what\_is\_the\_dom) <a href="#what_is_the_dom" id="what_is_the_dom"></a>

_Объектная Модель Документа (DOM)_ – это программный интерфейс (API) для HTML и XML документов. DOM предоставляет структурированное представление документа и определяет то, как эта структура может быть доступна из программ, которые могут изменять содержимое, стиль и структуру документа. Представление DOM состоит из структурированной группы узлов и объектов, которые имеют свойства и методы. По существу, **DOM соединяет веб-страницу с языками описания сценариев либо языками программирования.**

_Веб-страница_ – это документ. Документ может быть представлен как в окне браузера, так и в самом HTML-коде. В любом случае, это один и тот же документ. DOM предоставляет другой способ представления, хранения и управления этого документа. DOM полностью поддерживает объектно-ориентированное представление веб-страницы, делая возможным её изменение при помощи языка описания сценариев наподобие JavaScript.

### 11) Какие есть принципы тестирования?

1.  **1. Тестирование показывает наличие дефектов**

    Тестирование может показать наличие дефектов в программе, но не доказать их отсутствие. Тем не менее, важно составлять тест-кейсы, которые будут находить как можно больше багов. Таким образом, при должном тестовом покрытии, тестирование позволяет снизить вероятность наличия дефектов в программном обеспечении. В то же время, даже если дефекты не были найдены в процессе тестирования, нельзя утверждать, что их нет.

    **2. Исчерпывающее тестирование невозможно**

    Невозможно провести исчерпывающее тестирование, которое бы покрывало все комбинации пользовательского ввода и состояний системы, за исключениям совсем уж примитивных случаев. Вместо этого необходимо использовать анализ рисков и расстановку приоритетов, что позволит более эффективно распределять усилия по обеспечению качества ПО.

    **3. Раннее тестирование**

    Тестирование должно начинаться как можно раньше в жизненном цикле разработки программного обеспечения, и его усилия  должны быть сконцентрированы на определенных целях.

    **4. Скопление дефектов**

    Разные модули системы могут содержать разное количество дефектов – то есть, плотность скопления дефектов в разных элементах программы может отличаться. Усилия по тестированию должны распределяться пропорционально фактической плотности дефектов. В основном, большую часть критических дефектов находят в ограниченном количестве модулей. Это проявление принципа Парето: 80% проблем содержатся в 20% модулей.

    **5. Парадокс пестицида**

    Прогоняя одни и те же тесты вновь и вновь, Вы столкнетесь с тем, что они находят все меньше новых ошибок. Поскольку система эволюционирует, многие из ранее найденных дефектов исправляют и старые тест-кейсы больше не срабатывают.

    Чтобы преодолеть этот парадокс, необходимо периодически вносить изменения в используемые наборы тестов, рецензировать и корректировать их с тем, чтобы они отвечали новому состоянию системы и позволяли находить как можно большее количество дефектов.

    **6. Тестирование зависит от контекста**

    Выбор методологии, техники и типа тестирования будет напрямую зависеть от природы самой программы. Например, программное обеспечение для медицинских нужд требует гораздо более строгой и тщательной проверки, чем, скажем, компьютерная игра. Из тех же соображений, сайт с большой посещаемостью должен пройти через серьезное тестирование производительности, чтобы показать возможность работы в условиях высокой нагрузки.

    **7. Заблуждение об отсутствии ошибок.**

    Тот факт, что тестирование не обнаружило дефектов, еще не значит, что программа готова к релизу. Нахождение и исправление дефектов будут не важны, если система окажется неудобной в использовании, и не будет удовлетворять ожиданиям и потребностям пользователя.

    _И еще несколько важных принципов:_

    — тестирование должно производиться независимыми специалистами;

    — привлекайте лучших профессионалов;

    — тестируйте как позитивные, так и негативные сценарии;

    — не допускайте изменений в программе в процессе тестирования;

    — указывайте ожидаемый результат выполнения тестов.

### 12)Написание чек листов и тест кейсов, шаблон тест кейса

### 13)Severity and priority

**Серьезность** (**Severity**) - это атрибут, характеризующий влияние дефекта на работоспособность приложения.

**Приоритет** (**Priority**) - это атрибут, указывающий на очередность выполнения задачи или устранения дефекта. Можно сказать, что это инструмент менеджера по планированию работ. Чем выше приоритет, тем быстрее нужно исправить дефект.

Предположим, в некой системе не работает модуль отчетности. Это –дефект с уровнем серьезности «S1 Блокирующий». Однако этот модуль потребуется только в конце отчетного периода (перед Новым Годом). Если сейчас лето, то данная функциональность не будет использоваться еще несколько месяцев. Как следствие, руководитель проекта или лицо, принимающее решение, может проставить низкий приоритет исправления.

Обратная ситуация: на лицевой странице сайта (или интерфейса приложения) неправильно отображается какая-то важная надпись/логотип (например, название Компании). Данный дефект способен сильно ударить по доверию пользователей к продукции, которую им предлагают: потенциальные клиенты могут подумать, что качество услуг весьма сомнительно, раз даже в названии компании присутствует дефект – и отказаться от использования продукта. С точки зрения подхода к качеству, даже нефункциональные дефекты с уровнем серьезности «Тривиальный» способны отрицательно повлиять на репутацию Компании. Поэтому такому дефекту может быть проставлен высокий приоритет исправления.

### 14) Defect lifecicle

**Жизненный цикл дефекта** – это стадии, которые проходит ошибка с начала своего существования и до ее полного разрешения. Чтобы было проще воспринимать, жизненный цикл рисуют схематично, где отображаются все статусы и действия, которые эти статусы и сменяют.

![](<../.gitbook/assets/image (20) (1) (1) (1) (1) (1) (1) (1).png>)

### 15) Типы тестирования

![](<../.gitbook/assets/image (23) (1) (1) (1) (1) (1).png>)

### 16) Модели разработки (Agile)

![](<../.gitbook/assets/image (17) (1).png>)

![](<../.gitbook/assets/image (21) (1) (1) (1) (1).png>)

![](<../.gitbook/assets/image (18) (1) (1).png>)

![](<../.gitbook/assets/image (22) (1) (1) (1) (1).png>)

![](<../.gitbook/assets/image (19) (1) (1).png>)

### 17) Верификация и валидация

**Верификация (Verification)** — это **** статическая практика проверки документов, дизайна, архитектуры, кода, т.д.

* **Верификация —** это процесс включающий в себя проверку Plans, Requirement Specifications, Design Specifications, Code, Test Cases, Chek-Lists, etc.
* **Верификация** всегда проходит без запуска кода.
* **Верификация** использует методы — reviews, walkthroughs, inspections, etc.
* **Верификация** отвечает на вопрос “Делаем ли мы продукт правильно?”
* **Верификация** поможет определить, является ли программное обеспечение **высокого качества**, но оно не гарантирует, что система **полезна**. Проверка связана с тем, что система хорошо спроектирована и безошибочна.
* **Верификация** происходит до **Validation.**

**Валидация (validation)** – это процесс оценки конечного продукта, необходимо проверить, соответствует ли программное обеспечение ожиданиям и требованиям клиента. Это динамический механизм проверки и тестирования фактического продукта.

* **Валидация** всегда включает в себя запуск кода программы.
* **Валидация** использует методы, такие как тестирование Black Box, тестирование White Box и нефункциональное тестирование.
* **Валидация** отвечает на вопрос “Делаем ли мы правильный продукт?”
* **Валидация** проверяет, соответствует ли программное обеспечение требованиям и ожиданиям клиента.
* **Валидация** может найти ошибки, которые процесс **Verification** не может поймать.
* **Валидация** происходит после **Verification.**

На практике, отличия верификации и валидации имеют большое значение: заказчика интересует в большей степени валидация (удовлетворение собственных требований); исполнителя, в свою очередь, волнует не только соблюдение всех норм качества (верификация) при реализации продукта, а и соответствие всех особенностей продукта желаниям заказчика.

### 18)Клиент-серверная архитектура

Source: [https://habr.com/ru/post/495698/](https://habr.com/ru/post/495698/)

**Клиент** — та программа, с которой работает пользователь. Он знать не знает, это у него на компьютере программа целиком, или где-то за ней прячутся сервер с базой, а то и целый RAID. Он работает в браузере или с desktop-приложением. И всё, что ему нужно знать — это «куда тут тыкать».\
\
Клиенту не нужно много памяти, места на диске и других ресурсов. Поэтому рабочие места относительно дешево стоят. А это именно то, что нам нужно, особенно если нужно закупить оборудование для тысяч операционисток банка.\
\
**Сервер** — компьютер, на котором хранится само приложение. Весь код, вся логика, все дополнительные материалы и справочники. Например, справочник адресов ФИАС или справочник юр лиц ЕГРЮЛ — они тоже занимают место, как сами по себе, так и в памяти приложения.\
\
Иногда говорят «сервер приложения» и «сервер БД». Это нормально, ведь фактически сервер — это просто машина, компьютер. А базу и сервер приложения обычно хранят на разных машинах, ради безопасности. В таком случае, если говорят «сервер приложения» — речь о втором звене нашей схемы.\
\
Приложения бывают самые разные. Есть ресурсоемкие, им нужно много памяти и места на диске. Есть «легкие», которые можно развернуть даже на домашнем компьютере.\
\
**БД (база данных)** — хранилище данных. Тут вы можете легко поискать информацию + уверены в том, что она сохранится, даже если в приложении что-то сломается. \
\
Сколько места нужно под базу, зависит от количества данных. Есть огромные базы в банках, где и 1тб будет мало. А есть совсем небольшие, которые вы можете установить на своей машине. Например, [XAMPP](https://webdriver.ru/blog/2015-05-21-installing-xampp/) можно поставить. И врядли вы напихаете туда столько данных, что у вас не останется под них место.\
\
Отдельной базы может не быть, тогда структура станет двузвенной: клиент-сервер. И все!

### 19)Техники тест дизайна

Source: [https://quality-lab.ru/blog/roles-and-responsibilities-of-test-designer/](https://quality-lab.ru/blog/roles-and-responsibilities-of-test-designer/)

1. Тестирование Классами Эквивалентности (Equivalence Class Testing)\
   An equivalence class consists of a set of data that is treated the same by a module or that should produce the same result.
2. Тестирование Граничных Значений (Boundary Value Testing).\
   The boundaries — the “edges” of each equivalence class
3. Таблица Принятия Решений (Decision Table Testing).
4. Тестирование Состояний и Переходов (State-Transition Testing).
5. Метод Парного Тестирования (Pairwise testing).
6. Доменный анализ (Domain Analysis Testing).
7. Сценарий использования (Use Case Testing).

### 20) В чём разница между HTTP и HTTPS

По HTTP информация передаётся в обычном виде, а по HTTPS — в зашифрованном. Шифровать данные нужно, чтобы хакеры не смогли ничего прочитать, если перехватят их.

### 21)Как получить информацию из базы

Нужно записать свой запрос в понятном для базы виде — на SQL. _SQL (Structured Query Language)_ — язык общения с базой данных. В нем есть ключевые слова, которые помогут вам сделать выборку:

* _select_ — выбери мне такие-то колонки...
* _from_ — из такой-то таблицы базы...
* _where_ — такую-то информацию...

в SQL:

```
select * from clients where name = 'Назина Ольга';
```

### 22) Что такое API?

**API** (Application programming interface) —  описание способов которыми одна компьютерная программа может взаимодействовать с другой программой.

### 23) What is the key difference between CSS and XPath selectors?

Xpath:\
1\) bidirectional \
2\) can search by text

### 24) What is Closure?

A Closure is a combination of a function bundled together with references to its surrounding state (lexical environment). In other worlds, closure give you access to an outer scope function from inner function.

### 25) Typescript

1.  **What is TypeScript, and what are its benefits over JavaScript?**\


    TypeScript is an open-source programming language developed by Microsoft. It is a strict syntactical superset of JavaScript, meaning that it includes all of the features of JavaScript and adds additional syntax for defining types. TypeScript is designed to help developers write more robust and maintainable code by catching errors at compile-time rather than run-time.

    Some benefits of using TypeScript over JavaScript include:

    1. Type checking: TypeScript provides static type checking, which can help catch errors at compile-time rather than run-time. This can help improve code quality and reduce the likelihood of bugs in your code.
    2. Improved code organization: TypeScript allows developers to define interfaces and classes, which can help improve the organization and structure of code.
    3. Enhanced IDE support: Because TypeScript includes type information, IDEs such as Visual Studio Code can provide enhanced autocomplete and code navigation features.
    4. Better code maintainability: Because TypeScript provides better type checking and code organization, it can help make code more maintainable over time.
    5. Compatibility with existing JavaScript code: Because TypeScript is a superset of JavaScript, developers can use existing JavaScript code with TypeScript, making it easy to adopt in existing projects.


2.  **How does TypeScript support static typing, and what are its data types?**\
    ****\
    ****TypeScript supports static typing by allowing developers to define the data types of variables, function parameters, and function return values. TypeScript includes a set of built-in data types, including:

    1. Boolean: represents a boolean value (true or false)
    2. Number: represents a numeric value
    3. String: represents a string value
    4. Array: represents an array of values of a specific type
    5. Tuple: represents an array of values of different types
    6. Enum: represents a set of named constants
    7. Any: represents any type of value (similar to dynamic typing in JavaScript)
    8. Void: represents the absence of a value (typically used as the return type of functions that don't return a value)
    9. Null and Undefined: represents null or undefined values

    Developers can also define custom data types using interfaces or classes. Interfaces define the shape of an object, while classes define a blueprint for creating objects.

    By using static typing, TypeScript helps catch errors at compile-time, which can improve code quality and maintainability. Additionally, IDEs can use type information to provide enhanced code completion and navigation features.\

3.  **Explain the difference between "any" and "unknown" data types in TypeScript.**\
    ****\
    ****In TypeScript, both the "any" and "unknown" data types can be used to represent a value of any type. However, there are some important differences between these data types:

    1. "any": The "any" data type is used to indicate that a variable can be of any type. This means that TypeScript will not perform type checking on values of type "any". While this can be useful in some cases, it can also make code more error-prone and difficult to maintain.
    2. "unknown": The "unknown" data type is also used to indicate that a variable can be of any type. However, unlike the "any" type, TypeScript will perform type checking on values of type "unknown". This means that developers must perform a type check before using a value of type "unknown". While this can make code more verbose, it can also help catch errors at compile-time and improve code quality.

    In general, it's recommended to use the "unknown" type over the "any" type whenever possible, as it can help improve code quality and maintainability. However, there may be some cases where the "any" type is necessary (e.g., when working with third-party libraries that use dynamic typing).\

4.  **What is the purpose of the "interface" keyword in TypeScript, and how does it differ from a class?**\
    ****\
    ****In TypeScript, an interface is a way to define the shape of an object. An interface defines a set of properties and methods that an object must have to be considered of that interface type. The "interface" keyword is used to define an interface in TypeScript.

    For example, consider the following interface:\


    ```typescript
    interface Person {
      name: string;
      age: number;
      sayHello: () => void;
    }
    ```

    \
    This interface defines a type called "Person", which has three properties: "name" of type string, "age" of type number, and "sayHello" which is a function that takes no arguments and returns no value.

    Interfaces are often used to define the shape of data that is being passed between different parts of an application, such as between a frontend and backend API.

    A class, on the other hand, is used to define a blueprint for creating objects. A class can have properties, methods, and constructors, and can be used to create multiple instances of the same type of object.

    While there are some similarities between interfaces and classes (both can define properties and methods), the main difference is that an interface only defines the shape of an object, while a class defines both the shape and behavior of an object.

    In general, it's recommended to use interfaces to define the shape of data, and classes to define the behavior of objects.\

5.  **How does TypeScript support "generics," and what is their use case?**\
    ****\
    ****In TypeScript, "generics" are a way to create reusable code that can work with different types. Generics allow us to define a class, function, or interface in a way that can be used with multiple types, making our code more flexible and reusable.

    Here's an example of a generic function in TypeScript:\


    ```r
    function identity<T>(arg: T): T {
      return arg;
    }
    ```

    \
    In this example, the "\<T>" syntax is used to define a type parameter "T", which can be any type. The function takes an argument of type "T" and returns a value of the same type.

    We can call this function with any type we want, and TypeScript will perform type inference to determine the type of "T". For example:\


    ```scss
    const result1 = identity("hello"); // result1 is of type string
    const result2 = identity(42); // result2 is of type number
    ```

    \
    In addition to functions, generics can also be used with classes and interfaces. For example, we could define a generic interface like this:\


    ```csharp
    interface Collection<T> {
      items: T[];
      add(item: T): void;
      remove(item: T): void;
      get(index: number): T;
    }
    ```

    \
    In this example, the "Collection" interface is defined with a type parameter "T", which is used to define the type of items in the collection. We can then use this interface to create a collection of any type we want:\


    ```typescript
    const numbers: Collection<number> = {
      items: [1, 2, 3],
      add(item: number) {
        this.items.push(item);
      },
      remove(item: number) {
        const index = this.items.indexOf(item);
        if (index >= 0) {
          this.items.splice(index, 1);
        }
      },
      get(index: number) {
        return this.items[index];
      }
    };
    ```

    \
    In this example, we've created a collection of numbers by specifying "number" as the type parameter for the "Collection" interface.

    The use cases for generics are many, but some common scenarios include creating reusable data structures, creating functions that can work with different types of data, and creating type-safe APIs that can work with any data type. By using generics, we can write more flexible and reusable code that can work with different types without sacrificing type safety.\

6.  **Can you explain the concept of "decorators" in TypeScript, and provide an example of their usage?**\
    ****\
    ****In TypeScript, "decorators" are a feature that allows you to modify the behavior of a class, method, property, or parameter at runtime by wrapping them with a special function. Decorators are defined using the "@" symbol followed by the name of the decorator function, and can be used to add functionality to a class or to modify its behavior.

    Here's an example of a decorator that logs the name of a method whenever it's called:\


    ```typescript
    function logMethod(target: any, propertyKey: string, descriptor: PropertyDescriptor) {
      const originalMethod = descriptor.value;

      descriptor.value = function(...args: any[]) {
        console.log(`Calling method "${propertyKey}"`);
        return originalMethod.apply(this, args);
      };

      return descriptor;
    }

    class MyClass {
      @logMethod
      myMethod() {
        console.log('Inside myMethod');
      }
    }

    const myObject = new MyClass();
    myObject.myMethod();
    ```

    \
    In this example, we define a "logMethod" decorator function that takes three arguments: "target" (the class that the method belongs to), "propertyKey" (the name of the method), and "descriptor" (an object that describes the method). The decorator function then modifies the method by wrapping it with a function that logs the name of the method before calling the original method.

    We can then use the decorator by applying it to a method in a class using the "@" syntax, like this:\


    ```typescript
    @logMethod
    myMethod() {
      console.log('Inside myMethod');
    }
    ```

    \
    When the "myMethod" function is called, the decorator function is executed first, and the method is modified to include the logging behavior.

    Decorators can also be used to add metadata to classes or methods, to validate inputs or outputs, or to modify the behavior of properties or parameters.

    Here's an example of a decorator that adds metadata to a class:\


    ```kotlin
    @SomeMetadata('my metadata')
    class MyClass {
      // ...
    }
    ```

    \
    In this example, the "SomeMetadata" decorator adds metadata to the "MyClass" class, which can be used at runtime to provide additional information about the class.

    In summary, decorators are a powerful feature of TypeScript that allow you to modify the behavior of classes, methods, properties, or parameters at runtime by wrapping them with a special function. Decorators can be used to add functionality, modify behavior, or add metadata to your code, making it more flexible and extensible.\

7.  **What is "Type Assertion" in TypeScript, and how can it be used to improve code readability and maintainability?**\
    ****\
    ****In TypeScript, "type assertion" is a way to tell the compiler that a value is of a certain type, even if the compiler is not able to infer the type automatically. Type assertions allow you to bypass TypeScript's static type checking system and provide your own type information for a value.

    Type assertions are written using the "as" keyword followed by the desired type, like this:\


    ```typescript
    typescriptCopy codeconst myVariable: any = 'hello world';
    const myString: string = myVariable as string;
    ```

    \
    In this example, we use a type assertion to tell TypeScript that the "myVariable" variable should be treated as a string, even though it is declared as "any". This can be useful when working with values that have a more general type, such as "any", or when working with external libraries that don't have TypeScript type definitions.

    Type assertions can also be used to improve code readability and maintainability. By explicitly specifying the type of a value, you can make your code more self-documenting and easier to understand, especially for other developers who might not be familiar with your codebase.

    Here's an example of how type assertions can improve code readability:\


    ```typescript
    typescriptCopy codeinterface Person {
      name: string;
      age: number;
    }

    function getPerson(): any {
      return { name: 'John', age: 30 };
    }

    const person = getPerson() as Person;
    ```

    \
    In this example, we use a type assertion to tell TypeScript that the result of the "getPerson" function should be treated as a "Person" object, even though it is declared as "any". This makes the code more readable and easier to understand, especially if other developers are not familiar with the implementation of the "getPerson" function.

    Type assertions can also be used to improve code maintainability by catching errors early. If a type assertion is incorrect, TypeScript will raise a type error at compile-time, alerting you to the problem before it causes issues at runtime. By using type assertions to provide your own type information, you can catch potential errors and maintain the integrity of your codebase over time.

    In summary, type assertions are a powerful feature of TypeScript that allow you to provide your own type information for values, bypassing the compiler's static type checking system. Type assertions can improve code readability and maintainability by making your code more self-documenting and catching potential errors early. However, it's important to use type assertions judiciously and only when necessary, as incorrect type assertions can lead to runtime errors and other issues.\

8.  **Can you explain the concept of "Type Inference" in TypeScript, and provide an example of its usage?**\
    ****\
    ****In TypeScript, "type inference" is the process by which the compiler analyzes your code and automatically infers the types of variables, functions, and other elements based on their usage.

    Type inference allows you to write code that is statically typed without having to manually specify types for every variable and function parameter. Instead, TypeScript can often determine the type of a value based on the context in which it is used.

    For example, consider the following code:

    ```typescript
    typescriptCopy codeconst message = 'hello world';
    const count = 42;

    function add(a: number, b: number) {
      return a + b;
    }

    const result = add(count, 10);
    ```

    In this code, we declare two variables, "message" and "count", and a function "add" that takes two parameters of type "number". We then call the "add" function and assign the result to a variable "result".

    TypeScript is able to infer the types of "message" and "count" based on their initialization values, and it is able to infer the types of the "a" and "b" parameters in the "add" function based on the function signature. It is also able to infer the type of the "result" variable based on the return type of the "add" function.

    Type inference can be especially useful when working with complex data structures, such as arrays and objects. For example:

    ```javascript
    javascriptCopy codeconst users = [
      { name: 'Alice', age: 30 },
      { name: 'Bob', age: 40 }
    ];

    function getUserNames(users: { name: string }[]) {
      return users.map(user => user.name);
    }

    const names = getUserNames(users);
    ```

    In this code, we declare an array of user objects, and a function "getUserNames" that takes an array of user objects and returns an array of their names. We then call the "getUserNames" function and assign the result to a variable "names".

    TypeScript is able to infer the type of the "users" variable as an array of objects with "name" and "age" properties, and it is able to infer the type of the "user" parameter in the "getUserNames" function as an object with a "name" property. This allows us to write type-safe code without having to manually specify the types of every property and parameter.

    In summary, type inference is a powerful feature of TypeScript that allows the compiler to automatically infer the types of variables, functions, and other elements based on their usage. This can save you time and effort when writing code, and can make your code more readable and maintainable. However, it's important to be aware of the limitations of type inference and to manually specify types when necessary to ensure type safety and avoid errors.\
    ****
9.  **What are the differences between "let" and "const" in TypeScript, and when should you use each?**\
    ****

    In TypeScript (as well as in JavaScript), "let" and "const" are used to declare variables. Here are the differences between the two:

    1. Mutability: "let" is used to declare a variable whose value can be changed, whereas "const" is used to declare a variable whose value is immutable (i.e., cannot be changed).
    2. Scoping: Both "let" and "const" are block-scoped, meaning that they are only accessible within the block in which they are declared (e.g., a function, if statement, or loop). However, "let" allows you to redeclare the same variable within an inner block, whereas "const" does not.
    3. Initialization: When using "let", you can declare a variable without initializing it, and assign a value to it later. When using "const", you must declare and initialize the variable at the same time, and cannot reassign a new value to it later.

    Here are some general guidelines for when to use "let" versus "const":

    * Use "let" when you need to declare a variable whose value will change over time, or when you need to declare a variable without initializing it.
    * Use "const" when you need to declare a variable whose value will not change (e.g., a constant value or a reference to an immutable object), or when you want to prevent accidental reassignment of a variable.
    * It's worth noting that using "const" does not necessarily make your code more performant or efficient. It's primarily a tool for enforcing immutability and preventing errors caused by accidental variable reassignment.

    Here's an example of how you might use "let" and "const" in a TypeScript program:\


    ```javascript
    // Declare a mutable variable using let
    let count = 0;
    count = 1;
    console.log(count); // Output: 1

    // Declare an immutable variable using const
    const message = 'hello';
    console.log(message); // Output: hello

    // Declare an immutable variable referencing an object
    const user = { name: 'Alice', age: 30 };
    console.log(user.name); // Output: Alice
    user.age = 31; // This is allowed because the object is mutable
    console.log(user.age); // Output: 31

    // Declare a variable without initializing it
    let x;
    x = 10;
    console.log(x); // Output: 10
    ```

****
