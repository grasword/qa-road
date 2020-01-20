# Тестирование

## Unit testing

**Модульное тестирование**, иногда **блочное тестирование** или **юнит-тестирование** \(англ. unit testing\) — процесс в программировании, позволяющий проверить на корректность отдельные модули [исходного кода](https://ru.wikipedia.org/wiki/%D0%98%D1%81%D1%85%D0%BE%D0%B4%D0%BD%D1%8B%D0%B9_%D0%BA%D0%BE%D0%B4) программы, наборы из одного или более программных модулей вместе с соответствующими управляющими данными, процедурами использования и обработки.

Идея состоит в том, чтобы писать тесты для каждой нетривиальной функции или метода. Это позволяет достаточно быстро проверить, не привело ли очередное изменение кода к [регрессии](https://ru.wikipedia.org/wiki/%D0%A0%D0%B5%D0%B3%D1%80%D0%B5%D1%81%D1%81%D0%B8%D0%BE%D0%BD%D0%BD%D0%BE%D0%B5_%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5), то есть к появлению ошибок в уже оттестированных местах программы, а также облегчает обнаружение и устранение таких ошибок.

![](../.gitbook/assets/image.png)

## Integration Testing

  **Интеграционное тестирование** — одна из фаз [тестирования программного обеспечения](https://ru.wikipedia.org/wiki/%D0%A2%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5_%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%BD%D0%BE%D0%B3%D0%BE_%D0%BE%D0%B1%D0%B5%D1%81%D0%BF%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F), при которой отдельные программные модули объединяются и тестируются в группе. Обычно интеграционное тестирование проводится после [модульного тестирования](https://ru.wikipedia.org/wiki/%D0%9C%D0%BE%D0%B4%D1%83%D0%BB%D1%8C%D0%BD%D0%BE%D0%B5_%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5) и предшествует [системному тестированию](https://ru.wikipedia.org/wiki/%D0%A1%D0%B8%D1%81%D1%82%D0%B5%D0%BC%D0%BD%D0%BE%D0%B5_%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5).

  Интеграционное тестирование в качестве входных данных использует модули, над которыми было проведено модульное тестирование, группирует их в более крупные множества, выполняет тесты, определённые в плане тестирования для этих множеств, и представляет их в качестве выходных данных и входных для последующего системного тестирования.

  Целью интеграционного тестирования является проверка соответствия проектируемых единиц функциональным, приёмным и требованиям надежности. Тестирование этих проектируемых единиц — объединения, множества или группы модулей — выполняется через их интерфейс, с использованием тестирования «чёрного ящика».  
  
 В рамках интеграционного тестирования также может проводиться регрессионное тестирование с целью проверки сделанных в приложении или окружающей среде изменений и работоспособности унаследованной функциональности.

### **Уровни интеграционного тестирования:**

* **Компонентный интеграционный уровень** \(Component Integration testing\)

  > Проверяется взаимодействие между компонентами системы после проведения компонентного тестирования.

* **Системный интеграционный уровень** \(System Integration Testing\)

  > Проверяется взаимодействие между разными системами после проведения системного тестирования.

### **Подходы к интеграционному тестированию:**

* **Снизу вверх** \(Bottom Up Integration\)

  > Все низкоуровневые модули, процедуры или функции собираются воедино и затем тестируются. После чего собирается следующий уровень модулей для проведения интеграционного тестирования. Данный подход считается полезным, если все или практически все модули, разрабатываемого уровня, готовы. Также данный подход помогает определить по результатам тестирования уровень готовности приложения \(см. также [Integration testing - Bottom Up](http://en.wikipedia.org/wiki/Integration_testing#Bottom_Up)\)

* **Сверху вниз** \(Top Down Integration\)

  > Вначале тестируются все высокоуровневые модули, и постепенно один за другим добавляются низкоуровневые. Все модули более низкого уровня симулируются заглушками с аналогичной функциональностью, затем по мере готовности они заменяются реальными активными компонентами. Таким образом мы проводим тестирование сверху вниз. \(см. также [Top Down Integration](http://en.wikipedia.org/wiki/Integration_testing#Top-down_and_Bottom-up)\)

* **Большой взрыв** \("Big Bang" Integration\)

  > Все или практически все разработанные модули собираются вместе в виде законченной системы или ее основной части, и затем проводится интеграционное тестирование. Такой подход очень хорош для сохранения времени. Однако если тест кейсы и их результаты записаны не верно, то сам процесс интеграции сильно осложнится, что станет преградой для команды тестирования при достижении основной цели интеграционного тестирования \(см. также [Integration testing - Big Bang](http://en.wikipedia.org/wiki/Integration_testing#Big_Bang)\)

### **Преимущества интеграционного тестирования**:

Интеграционное тестирование позволяет имитировать действия пользователей и быстро получать подтверждение, что программный продукт успешно взаимодействует с другими системами. Такой подход гарантирует сразу несколько преимуществ:

1. Предотвращение появления критичных ошибок в опытно-промышленной эксплуатации
2. Снижение влияния человеческого фактора
3. Экономия затрат на исправление дефектов

### Основные этапы **интеграционного тестирования**:

* Разработка тест-плана – руководства к действию для тестировщиков;
* Формирование тестовых данных и создание тест-кейсов;
* Реализация сценариев для запуска тест-кейсов;
* Выполнение тест-кейсов и исправление ошибок;
* Повторение цикла тестирования до успешной интеграции.

## Functional testing

  **Функциональное тестирование** является одним из ключевых видов тестирования, задача которого – установить соответствие разработанного программного обеспечения \(ПО\) исходным функциональным требованиям заказчика. То есть проведение функционального тестирования позволяет проверить способность информационной системы в определенных условиях решать задачи, нужные пользователям.

  **Функциональные тесты** основываются на функциях, выполняемых системой, и могут проводиться на всех уровнях тестирования \(компонентном, интеграционном, системном, приемочном\). Как правило, эти функции описываются в требованиях, функциональных спецификациях или в виде случаев использования системы \(**use cases**\).

Тестирование функциональности может проводиться в двух аспектах:

* требования
* бизнес-процессы

  Тестирование в перспективе «требования» использует спецификацию функциональных требований к системе как основу для дизайна тестовых случаев \(**Test Cases**\). В этом случае необходимо сделать список того, что будет тестироваться, а что нет, приоритезировать требования на основе рисков \(если это не сделано в документе с требованиями\), а на основе этого приоритезировать тестовые сценарии \(test cases\). Это позволит сфокусироваться и не упустить при тестировании наиболее важный функционал.

  Тестирование в перспективе «бизнес-процессы» использует знание этих самых бизнес-процессов, которые описывают сценарии ежедневного использования системы. В этой перспективе тестовые сценарии \(**test scripts**\), как правило, основываются на случаях использования системы \(use cases\).

### **Преимущества функционального тестирования**:

* Функциональное тестирование ПО полностью имитирует фактическое использование системы.
* Позволяет своевременно выявить системные ошибки ПО и, тем самым, избежать множества проблем при работе с ним в дальнейшем.
* Экономия за счет исправления ошибок на более раннем этапе жизненного цикла ПО.

### **Недостатки функционального тестирования**:

* возможность упущения логических ошибок в программном обеспечении;
* вероятность избыточного тестирования.

### Типы функционального тестирования

  В зависимости от степени доступа к коду системы можно выделить два типа функциональных испытаний:

* тестирование **black box** \(черный ящик\) – проведение функционального тестирования без доступа к коду системы,
* тестирование **white box** \(белый ящик\) – функциональное тестирование с доступом к коду системы.

Тестирование **black box** проводится без знания внутренних механизмов работы системы и опирается на внешние проявления ее работы. При этом тестировании проверяется поведение ПО при различных входных данных и внутреннем состоянии систем.

В случае тестирования **white box** создаются тест-кейсы, основанные преимущественно на коде системы ПО. Также существует расширенный тип black-box тестирования, включающего в себя изучение кода, – так называемый grey box \(серый ящик\).

### Основные этапы функционального тестирования

  **Подготовка -** Проводится анализ исходных документов о системе: функциональные и бизнес-требования, техническое задание, паспорт проекта. Также происходят разработка и согласование плана тестирования, тест-кейсов, согласование проектных сроков, числа итераций, оценка возможных рисков. Задачи по этому этапу выполняются совместно с представителями заказчика.

  **Проведение -** Функциональное тестирование ведется вручную по подготовленным заранее тестовым сценариям с занесением всех найденных ошибок в багтрекинговую систему. В случае отсутствия такой системы у заказчика мы можем: предоставить систему управления тестированием на своей площадке; поставить заказчику лицензии; использовать имеющиеся у заказчика средства; обходиться только офисным пакетом; поставить процесс тестирования у заказчика на основе бесплатных средств.

  **Отчет -** Происходит разработка и согласование отчетов о проведенном тестировании со списком обнаруженных отклонений и рекомендациями по улучшению системы. Если необходимо, проводится обучение пользователей.

## System Testing

## Acceptance Testing \(Smoke testing\)

## Regression Testing

## Black-Box/White Box Testing

## Test automatization
