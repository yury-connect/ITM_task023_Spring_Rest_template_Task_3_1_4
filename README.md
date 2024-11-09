# Задача: **PP 3.1.4.**

---

#### Тема: _10 Spring_
#### № **ITMPJ-2764**
#### Наименование: _Микросервисная система_
#### Дедлайн: _25/11/2024_
#### Код модуля: _PP3_ //  _PreProject3_

---
# Микросервисная система

### В рамках этой задачи мы освоим работу с Rest-template, взаимодействуя с помощью него с открытым Rest API.:

### Для выполнения задания необходимо::

> 1. Создать Maven проект
> 2. Включить в файл `pom.xml` необходимые зависимости


### Описание задачи:

> Для работы предоставляется API по URL - *http://94.198.50.185:7081/api/users*
>
> 1. Написать `Rest`-контроллеры для вашего приложения.;
> 2. Необходимо установить `Postman`/`Insomnia` и разобраться как он работает;
> 3. С помощью `Postman`/`Insomnia` протестировать все `Rest endpoints`.

### Ваша задача:

> Последовательно выполнить следующие операции и получить код для проверки на платформе:
>
> 1. Получить список всех пользователей;
>
> 2. Когда вы получите ответ на свой первый запрос, вы должны сохранить свой session id,
     >  который получен через cookie. Вы получите его в заголовке ответа set-cookie. Поскольку все
     > действия происходят в рамках одной сессии, все дальнейшие запросы должны использовать
     >  полученный session id ( необходимо использовать заголовок в последующих запросах );
>
> 3. Сохранить пользователя с `id = 3`, `name = James`, `lastName = Brown`, `age = на ваш выбор`.
     >  В случае успеха вы получите первую часть кода.;
>
> 4. Изменить пользователя с `id = 3`. Необходимо поменять `name` на `Thomas`, а `lastName`
     >  на `Shelby`. В случае успеха вы получите еще одну часть кода.;
>
> 5. Удалить пользователя с `id = 3`. В случае успеха вы получите последнюю часть кода.
>
> В результате выполненных операций вы должны получить итоговый код,
>  сконкатенировав все его части. Количество символов в коде = `18`.
>

### Необходимые данные:

> _Модель пользователя:_
> ```java
> {{ public class User
>
> {   private Long id;   private String name;   private String lastName;   private Byte age; ... }
>
> }}
> ```
>

### Список URL для операций и типы запросов::

> 1. Получение всех пользователей - `…/api/users` **( GET )**
> 2. Добавление пользователя - `…/api/users` **( POST )**
> 3. Изменение пользователя - `…/api/users` **( PUT )**
> 4. Удаление пользователя - `…/api/users */ {id} *` **( DELETE )**


### Требования:

> 1. Все операции должны проводится в рамках одной сессии (не пытайтесь выполнить
>  операции в ручную, например через POSTMAN, сессия имеет ограниченное время жизни);
>
> 2. Все операции должны быть выполнены последовательно по условию;
>
> 3. Для того, чтобы получить необходимый заголовок из запроса, необходимо
>  использовать тип данных `ResponseEntity **` в качестве ответа на ваш запрос.;
>

---

## В этой теме Вы изучите
* Spring Boot
* Spring Security
* Rest
* Микросервисы

---

[Ссылка на оригинальную страницу](http://jira.it-mentor.tech/browse/ITMPJ-2764)

[Ссылка на данную страницу](https://github.com/yury-connect/ITM_task023_Spring_Rest_template_Task_3_1_4.git)

---

## Документирую код выполненного задания по **PP 3.1.4**.

> [**ССЫЛКА**](http://localhost:8088/api/users/execute_scrypt) на запуск скрипта _(на ПК)_ 
> // Удаленный сервер вернется код `5ebfebe7cb975dfcf9`
>
> [**ССЫЛКА**](http://localhost:8088/swagger-ui/index.html?configUrl=/v3/api-docs/swagger-config) 
> просмотреть маршруты через `swagger-ui` _(скрин ниже, но можно просматривать детали по маршрутам)_

> > **GET** `/api/users/` Получение всех пользователей (GET)
> >
> > **POST** `/api/users/` Создание одного нового пользователя (POST)
> >
> > **PUT** `/api/users/{id}` Обновление данных существующего пользователя (PUT)
> >
> > **DELETE** `/api/users/{id}` Удаление пользователя по ID (DELETE)
> >
> > **GET** `/api/users/execute_scrypt` Выполнить полный скрипт и получить код согласно задания (GET)
> >
>
> > #### Скрин ниже:
> ![скрин](/imgs/2024-11-09_19-52-13.png)
>
> Полный список маршрутов можно получить через модуль SWAGER, перейдя по [ссылке](http://localhost:8088/swagger-ui/index.html?configUrl=/v3/api-docs/swagger-config) при запущеном проекте.
> _http://localhost:8088/swagger-ui/index.html?configUrl=/v3/api-docs/swagger-config_
>

### Иерархия файлов проекта:
```text
ITM_task023_Spring_RestTemplate_Task_3_1_4
src
└──main
   ├───java
   │   └───ru
   │       └───itmentor
   │           └───spring
   │               └───rest
   │                   └───template
   │                       │   Application.java
   │                       │   ServletInitializer.java
   │                       │
   │                       ├───config
   │                       │       AppConfig.java
   │                       │       SecurityConfig.java
   │                       │
   │                       ├───constants
   │                       │       Constants.java
   │                       │
   │                       ├───controller
   │                       │       RestTemplateUserController.java
   │                       │       RestTemplateUserControllerImpl.java
   │                       │
   │                       ├───model
   │                       │       AuthToken.java
   │                       │       User.java
   │                       │
   │                       └───service
   │                               UserServiceApi.java
   │                               UserServiceApiImpl.java
   │
   └───resources
       │   application.properties
       │   banner.txt
       │
       └───postman
               IT-Mentor_collection_v2.postman
               IT-Mentor_collection_v2_1.postman
```
