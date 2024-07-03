# Api for Toys Library project

### Метод получения всех активных мастер-классов

Возвращает ```json``` с данными *активных* **мастер-классов**, отсортированных по *дате*. Указывая query параметры, можно реализовать запрос, как на массив из 1 элемента, так и на множество.

* **URL**
```/master-classes```
* **Method**
 ```GET```
* **Query Params**
  ```
  offset=[integer] //optional
  ```

  ```
  limit=[integer] //required
  ```

* **Success Response:**
  * **Code:** 200
  * **Content:**

  ```
  [
    {
      idMasterClass: 10,
      name: 'Мыловарение',
      shortDescription: 'Здесь короткое описание МК Мыловарения',
      description: 'Здесь будет текст описывающий МК Мыловарения',
      price: 1990,
      startDate: '2011-10-05T14:48:00.000Z',
      imageUrlMasterClass: 'http://dummyimage.com/120'
    }
  ]
  ```

* **Error Response:**
  * **Code:** 400
  * **Content:**

    ```
    [
      {
        title: 'INCORRECT_PARAMETERS',
        detailError: 'Wrong parameters:...',
        request: 'GET /gallery',
      }
    ]
    ```
  * **Code:** 404
  * **Content:**

    ```
    [
      {
        title: 'NOT_FOUND',
        detailError: 'Entity does not exist',
        request: 'GET /gallery',
      }
    ]
    ```

### Метод получения отзывов

Возвращает ```json``` с данными **отзывов** отсортированных по дате добавления (от новых к старым).

* **URL**
```/feedbacks```
* **Method**
 ```GET```
* **Query Params**
  ```
  offset=[integer] //optional
  ```
  ```
  limit=[integer] //required
  ```
* **Success Response:**
  * **Code:** 200
  * **Content:**
    ```
    [
      {
        idFeedback: 10,
        imageURLFeedback: 'http://dummyimage.com/120',
        title: 'Отзывы',
        subtitle: 'Мы ценим каждого',
      }
    ]
    ```
* **Error Response:**
  * **Code:** 400
  * **Content:**

    ```
    [
      {
        title: 'INCORRECT_PARAMETERS',
        detailError: 'Wrong parameters:...',
        request: 'GET /gallery',
      }
    ]
    ```
  * **Code:** 404
  * **Content:**

    ```
    [
      {
        title: 'NOT_FOUND',
        detailError: 'Entity does not exist',
        request: 'GET /gallery',
      }
    ]
    ```
### Метод получения контактов организации

Возвращает ```json``` с данными **контакта** организации, т.к. на данный момент организация одна и контакт 1. Т.е. массив будет содержать 1 элемент

* **URL**
```/contacts```
* **Method**
 ```GET```
* **Query Params**
  ```
  offset=[integer] //optional
  ```
  ```
  limit=[integer] //required
  ```
* **Success Response:**
  * **Code:** 200
  * **Content:**
    ```
    [
      {
        idContact: 10,
        phoneNumber: '8-977-777-77-77',
        email: library@email.com,
        links: ['https://vk.com/twotoy', 'https://t.me/username'],
        address: 'г.Нижний Новгород ул.Котейкино, 23Б',
        location: 'https://yandex.ru/maps/47/nizhny-novgorod/house/puteyskaya_ulitsa_23b/YEoYfgFhTUMCQFtsfX54c3xhZw==/?ll=43.861466%2C56.292023&z=17'
        timeSchedule: {
          'monday': '10:00-20:00',
          'tuesday':'10:00-20:00'
          'wednesday': '10:00-20:00'
          'thursday': '10:00-20:00'
          'friday': '10:00-20:00'
          'saturday': '10:00-20:00'
          'sunday': '10:00-20:00'
        }
      }
    ]

    ```
  * **Error Response:**
  * **Code:** 400
  * **Content:**

    ```
    [
      {
        title: 'INCORRECT_PARAMETERS',
        detailError: 'Wrong parameters:...',
        request: 'GET /gallery',
      }
    ]
    ```
  * **Code:** 404
  * **Content:**

    ```
    [
      {
        title: 'NOT_FOUND',
        detailError: 'Entity does not exist',
        request: 'GET /gallery',
      }
    ]
    ```

### Метод получения всех сотрудников

Возвращает ```json``` с данными всех **сотрудников**.

* **URL**
```/employees```
* **Method**
 ```GET```
* **Query Params**
None
* **Success Response:**
  * **Code:** 200
  * **Content:**
    ```
    [
      {
        idEmployee: 10,
        lastName: 'Сергеев',
        firstName: 'Иван',
        patronymic: 'Петрович',
        position: 'Мастер по ремонту игрушек',
        description: 'Здесь будет текст про выдающиеся способности мастера по ремонту',
        avatarUrl: 'http://dummyimage.com/120',
      }
    ]
    ```
* **Error Response:**
  * **Code:** 404
  * **Content:**

    ```
    [
      {
        title: 'NOT_FOUND',
        detailError: 'Entity does not exist',
        request: 'GET /gallery',
      }
    ]
    ```

### Метод получения всех абонементов

Возвращает ```json``` с данными всех **абонементов**.

* **URL**
```/memberships```
* **Method**
 ```GET```
* **Query Params**
None
* **Success Response:**
  * **Code:** 200
  * **Content:**
    ```
    [
      {
        idMembership: 10,
        typeMembership: basic,
        name: 'Базовый',
        description: 'Здесь будет текст описывающий Базовый абонемент',
        price: 590,
      }
    ]
    ```
* **Error Response:**
  * **Code:** 404
  * **Content:**

    ```
    [
      {
        title: 'NOT_FOUND',
        detailError: 'Entity does not exist',
        request: 'GET /gallery',
      }
    ]
    ```

### Метод получения данных блока экологии

Возвращает ```json``` с данными для блока **Экология**, состоящий из текстовых блоков. Данный метод позволяет получить массив всех текстовых блоков

* **URL**
```/eco```
* **Method**
 ```GET```
* **Query Params**
None
* **Success Response:**
  * **Code:** 200
  * **Content:**
    ```
    [
      {
        idParagraph: 10,
        paragraphText: 'Дадим вторую жизнь вашим игрушкам',
      }
    ]
    ```

* **Error Response:**
  * **Code:** 404
  * **Content:**

    ```
    [
      {
        title: 'NOT_FOUND',
        detailError: 'Entity does not exist',
        request: 'GET /gallery',
      }
    ]
    ```

### Метод получения данных стартового экрана

Возвращает ```json``` с данными для  **стартового экрана**.

* **URL**
```/start-screen```
* **Method**
 ```GET```
* **Query Params**
None
* **Success Response:**
  * **Code:** 200
  * **Content:**
    ```
    {
      slogan: ['Новая игрушка хоть каждый день. Вы можете играть, делиться и меняться игрушками вместе с нами!'],
    }
    ```
* **Error Response:**
  * **Code:** 404
  * **Content:**

    ```
    [
      {
        title: 'NOT_FOUND',
        detailError: 'Entity does not exist',
        request: 'GET /gallery',
      }
    ]
    ```

### Метод получения данных раздела сайта по атрибуту slug

Возвращает ```json``` с данными для  **раздела сайта**.

* **URL**
```/sections/slug```
* **Method**
 ```GET```
* **URL Params**
 **Required:**
```slug={string}```
* **Query Params**
None
* **Data Params**
None
* **Success Response:**
  * **Code:** 200
  * **Content:**
    ```
    {
        slug:  'sbor-igrushek',
        title:  'Сбор игрушек',
        shortDescription: 'Здесь короткое описание для раздела Сбор игрушек',
        description: 'Здесь будет текст для раздела Сбор игрушек',
        images: ['http://dummyimage.com/120'],
    }
    ```
* **Error Response:**
  * **Code:** 400
  * **Content:**

    ```
    [
      {
        title: 'INCORRECT_PARAMETERS',
        detailError: 'Wrong slug',
        request: 'GET /sections/slug',
      }
    ]
    ```
* **Error Response:**
  * **Code:** 404
  * **Content:**

    ```
    [
      {
        title: 'NOT_FOUND',
        detailError: 'Entity does not exist',
        request: 'GET /gallery',
      }
    ]
    ```
### Метод получения данных всех разделов сайта

Возвращает ```json``` с данными для  **разделов сайта**.

* **URL**
```/sections```
* **Method**
 ```GET```
* **URL Params**
 **Required:**
```slug={string}```
* **Query Params**
None
* **Data Params**
None
* **Success Response:**
  * **Code:** 200
  * **Content:**
    ```
    [
      {
        slug:  'sbor-igrushek',
        title:  'Сбор игрушек',
        shortDescription: 'Здесь короткое описание для раздела Сбор игрушек',
        description: 'Здесь будет текст для раздела Сбор игрушек',
        images: ['http://dummyimage.com/120'],
      }
    ]
    ```
* **Error Response:**
  * **Code:** 404
  * **Content:**

    ```
    [
      {
        title: 'NOT_FOUND',
        detailError: 'Entity does not exist',
        request: 'GET /gallery',
      }
    ]
    ```

### Метод получения изображений для галереи

Возвращает ```json``` с данными для отображения изображений в  **галереи**.

* **URL**
```/gallery```
* **Method**
 ```GET```
* **Query Params**
  ```
  offset=[integer] //optional
  ```
  ```
  limit=[integer] //required
  ```
* **Data Params**
None
* **Success Response:**
  * **Code:** 200
  * **Content:**

  ```

    {
       ['http://dummyimage.com/120', 'http://dummyimage.com/240']
    }

  ```
* **Error Response:**
  * **Code:** 400
  * **Content:**

    ```
    [
      {
        title: 'INCORRECT_PARAMETERS',
        detailError: 'Wrong parameters:...',
        request: 'GET /gallery',
      }
    ]
    ```
* **Error Response:**
  * **Code:** 404
  * **Content:**

    ```
    [
      {
        title: 'NOT_FOUND',
        detailError: 'Entity does not exist',
        request: 'GET /gallery',
      }
    ]
    ```

### Метод создания заявки на обратный звонок администратора

Создает заявку на обратный звонок администратора, в случае успеха заявке присваивается идентификационный номер.

* **URL**
```/call-me```
* **Method**
 ```POST```
* **Query Params**
None
* **Data Params**

  ```
  {
      name:  'Аврора',
      phone: '8-977-777-77-77',
      email: '<tryl@email.com>',
      message: 'Хочу узнать про запись на МК',
  }
  ```

* **Success Response:**
  * **Code:** 200
  * **Content:**
    ```
    {
      idCallMe: '3422b448-2460-4fd2-9183-8000de6f8343',
      name:  'Аврора',
      phone: '8-977-777-77-77',
      email: '<tryl@email.com>',
      message: 'Хочу узнать про запись на МК',
    }
    ```

  ```
* **Error Response:**
  * **Code:** 500
  * **Content:**

    ```
      {
        title: 'INTERNAL SERVER ERROR',
        detailError: 'It was not created',
        request: 'POST /call-me',
      }
    ```