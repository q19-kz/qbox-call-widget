# Создание/обновление данных клиента

1) Создание клиента при отсуствии записи в БД
2) Обновление данных клиента при наличии записи в БД

### Request

URL:
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
    "birthdate": "<Дата рождения в формате DD.MM.YYYY>"
}
```

### Response:

JSON Body:
```json
{
    "data": {
        "customer": {
            "user_id": "<ID клиента>"
        }
    }
}
```
