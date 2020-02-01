# Тест-кейсы

## **Что такое тест-кейс?**

**Тест-кейс** — это профессиональная документация тестировщика, последовательность действий направленная на проверку какого-либо функционала, описывающая как придти к фактическому результату. Набор тест-кейсов называют тест-комплектом. Иногда тест-набор путают с тест-планом. Тест-план описывает какие работы, как и когда должны быть проведены в рамках тестирования продукта, а так же что необходимо для их выполнения.

## **Зачем нужны тест-кейсы?**

Тест-кейсы должен помочь нам провести проверку продукта без ознакомления с всей документацией. Написанный один раз, удобный в поддержке тест-кейс сэкономит много времени и сил тестировщикам.

## Атрибуты **тест-кейса**

 Любой тест-кейс обязательно включает в себя:

* **Уникальный идентификатор тест-кейса** — необходим для удобной организации хранения и навигации по нашим тест-наборам.
* **Название** — основная тема, или идея тест-кейса. Кратное описание его сути.
* **Предусловия** — описание условий, которые не имеют прямого отношения к проверяемому функционалу, но должны быть выполнены. Например, оставить комментарий на вашем портале может только зарегистрированный пользователь. Значит для тест-кейса «Создание комментария» будет необходимо выполнение предусловия «пользователь зарегистрирован», и «пользователь авторизован»
* **Шаги** — описание последовательности действий, которая должна привести нас к ожидаемому результату
* **Ожидаемый результат** — результат: что мы ожидаем увидеть после выполнения шагов.

Не обязательно, но желательно добавить в тест-кейс атрибут **история редактирования** — это сильно облегчит вам жизнь. Лаконичный журнал изменений, где отраженно: кем, как, и когда был изменен тест-кейс.

## **Что еще необходимо знать, перед созданием тест-кейса?**

Во-первых, каждый выполненный тест-кейс, дает нам один из трех результатов:  
  
1.**Положительный результат**, если фактический результат равен ожидаемому результату,  
2.**Отрицательный результа**т, если фактический результат не равен ожидаемому результату. В этом случае, найдена ошибка.  
3.**Выполнение теста блокировано**, если после одного из шагов продолжение теста невозможно. В этом случае так же, найдена ошибка.  
  
Во-вторых, одним тест-кейсом проверяется одна конкретная вещь, и для этой вещи должен быть только один ожидаемый результат.

## **Чего не должно быть в тест-кейсе**

1. Зависимостей от других тест-кейсов;  
2. Нечеткой формулировки шагов или ожидаемого результата;  
3. Отсутствия необходимой для прохождения тест-кейса информации;  
4. Излишней детализации.  
  
Первого следует избегать, потому что: связанный тест-кейс всегда может быть удален из-за ненадобности или он может быть изменен, в этом случае, станет непонятно как исполнить тест-кейс в которому, есть ссылки.  
  
Так же из-за зависимости тест-кейсов, может возникнуть ощущение, что тестируемый продукт уже приведет к нужному состоянию благодаря выполнению связанных тест-кейсов.  
  
Со вторым думаю все ясно. Если описание шагов или ожидаемое результата будет не четким, то это блокирует прохождение тест-кейса.  
  
В тест-кейса должно быть вся информация, которая необходима для его прохождения. Например, если мы проверяем окно логина на сайте, значит нам понадобится логин и пароль, иначе прохождение этого сценария будет невозможно.  
  
Так же не следует слишком детализировать кейс. Например, если мы проверяем возможность создания комментария, то не стоит писать в каком угле экрана должно быть окно логина. Избыточная информация только затрудняет прохождение тест-кейса.
