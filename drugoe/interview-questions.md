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

![](<../.gitbook/assets/image (20) (1) (1).png>)

### 15) Типы тестирования

![](<../.gitbook/assets/image (23) (1) (1) (1).png>)

### 16) Модели разработки (Agile)

![](<../.gitbook/assets/image (17).png>)

![](<../.gitbook/assets/image (21) (1) (1).png>)

![](<../.gitbook/assets/image (18).png>)

![](<../.gitbook/assets/image (22) (1) (1).png>)

![](<../.gitbook/assets/image (19).png>)

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

1. Тестирование Классами Эквивалентности (Equivalence Class Testing).
2. Тестирование Граничных Значений (Boundary Value Testing).
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

****

****
