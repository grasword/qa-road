# Методы

 HTTP определяет множество **методов запроса**, которые указывают, какое желаемое действие выполнится для данного ресурса. Несмотря на то, что их названия могут быть существительными, эти методы запроса иногда называются _HTTP глаголами_. Каждый реализует свою семантику, но каждая группа команд разделяет общие свойства: так, методы могут быть [безопасными](https://developer.mozilla.org/ru/docs/%D0%A1%D0%BB%D0%BE%D0%B2%D0%B0%D1%80%D1%8C/safe), [идемпотентными](https://developer.mozilla.org/ru/docs/%D0%A1%D0%BB%D0%BE%D0%B2%D0%B0%D1%80%D1%8C/idempotent) или [кэшируемыми](https://developer.mozilla.org/ru/docs/%D0%A1%D0%BB%D0%BE%D0%B2%D0%B0%D1%80%D1%8C/cacheable).

* Метод[`GET`](https://developer.mozilla.org/ru/docs/Web/HTTP/Methods/GET) запрашивает представление ресурса. Запросы с использованием этого метода могут только извлекать данные.
* [`HEAD`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/HEAD) запрашивает ресурс так же, как и метод GET, но без тела ответа.
* [`POST`](https://developer.mozilla.org/ru/docs/Web/HTTP/Methods/POST) используется для отправки сущностей к определённому ресурсу. Часто вызывает изменение состояния или какие-то побочные эффекты на сервере.
* [`PUT`](https://developer.mozilla.org/ru/docs/Web/HTTP/Methods/PUT) заменяет все текущие представления ресурса данными запроса.
* [`DELETE`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/DELETE) удаляет указанный ресурс.
* [`CONNECT`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/CONNECT) устанавливает "туннель" к серверу, определённому по ресурсу.
* [`OPTIONS`](https://developer.mozilla.org/ru/docs/Web/HTTP/Methods/OPTIONS) используется для описания параметров соединения с ресурсом.
* [`TRACE`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/TRACE)выполняет вызов возвращаемого тестового сообщения с ресурса.
* [`PATCH`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PATCH) используется для частичного изменения ресурса.



