# Создание/обновление данных клиента

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
    "birthdate": "<Дата рождения в формате DD.MM.YYYY>",
}
```
