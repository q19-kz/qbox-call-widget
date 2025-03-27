# Поиск информации о сотруднике по внешнему ID

### Request

URL:
```
POST https://<domain>/bridge/api/v1/staff/employees/lookup
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
    "external_ids": ["<Внешний ID сотрудника>"]
}
```

### Response:

JSON Body:
```json
{
    "data": {
        "employees": [
            {
                "id": 12345,
                "external_id": "<Внешний ID сотрудника>",
                "username": "<Имя пользователя сотрудника>",
                "first_name": "<Имя сотрудника>",
                "last_name": "<Фамилия сотрудника>",
                "patronymic": "<Отчество сотрудника>"
            }
        ],
        "total": 1
    }
}
```
