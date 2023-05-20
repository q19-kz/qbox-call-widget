# qbox-widget-video-call

# Шаг 1. Добавление виджета

Добавить JavaScript библиотеку в ```<body></body>```. Запуск виджета в зависимости от требований бизнес-логики

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Video call sample</title>

  <style>
    html, body {
      margin: 0;
      padding: 0;
      height: 100%;
    }
  </style>
</head>
<body>

  <!-- Подключение JavaScript скрипта -->
  <script src="https://<domain>/static/js/wc-video-call.min.js"></script>  

  <!-- Пустой контейнер для будущего добавления виджета с видеозвонком -->
  <div id="video-call-wrapper"></div>
  
  <!-- Запуск виджета с видеозвонком -->
  <script>
    let videoCallElem = document.createElement("wc-video-call");  // Обязательное название 'wc-video-call'
    videoCallElem.setAttribute("host-name", "https://<domain>");
    videoCallElem.setAttribute("domain", "<domain>");  // Идентификатор интеграционной платформы
    videoCallElem.setAttribute("topic", "test");  // Тема звонка для маршрутизации
    videoCallElem.setAttribute("height", "100vh");  // Высота страницы виджета. По умолчанию "100vh"
    videoCallElem.setAttribute("request-call-feedback", 0);  // Управление над просьбой отзыва о звонке после завершения. 0 = убрать, 1 = добавить. По умолчанию значение 1
    videoCallElem.setAttribute("target-operator-id", 59);  // ID сотрудника в системе для точечной связи с конкретной оператором
    videoCallElem.setAttribute("user-id", 435);  // ID звонящего клиента в системе

    document.getElementById("video-call-wrapper").appendChild(videoCallElem);
  </script>  
  
</body>
</html>
```



# Шаг 2. Создание клиента

> при наличии клиента по указанным критериям выполнится только обновление данных и возврат ID клиента (upsert)

```
POST https://<domain>/bridge/api/v1/customers
```

Headers:
```json
{
    "X-API-Secret": "abcdefghijklmnopq"
}
```

JSON Body:
```json
{
    "first_name": "<Имя>",
    "last_name": "<Фамилия>",
    "patronymic": "<Отчество>",
    "sex": "<Пол: мужчина = 0, женщина = 1>",
    "iin": "<ИИН>",
    "email": "<Электронная почта>",
    "phone": "<Номер телефона в формате 77771234567>",
    "birthdate": "<День рождения в формате DD.MM.YYYY>",
}
```

* first_name, last_name, iin, phone являются обязательными параметрам, остальные опциональные

Ответ:
```json
{
    "data": {
        "customer": {
            "id": "<ID клиента в системе>"
        }
    },
    "_success": true
}
```



# Шаг 3. Запуск виджета

- Полученное ID клиента из [Шаг 2]() передать в качестве ```user-id``` как указано в [Шаг 1]()
- Запуск
