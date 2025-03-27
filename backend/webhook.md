Конец звонка (оператор вручную заполнил форму пост-обработки с результатом и завершил звонок)

1) Успешно:

```
{
    "call": {
        "id": "6617af94da2031d58b99d515",
        "datetime": "1970-01-01T23:59:59+05:00"
    },
    "user": {
        "id": "1321545",
        "iin": "901020304050",
        "phone": "77771234567",
        "external_id": "abd41b46-8ad1-4109-9377-eede58ce7c69"
    },
    "operator": {
        "id": 123456,
        "username": "random_someone"
    },
    "status": "success",
    "tech_error_reason": null,
    "comment": null
}
```

---

2) Неуспешно:

```
{
    "call": {
        "id": "6617af94da2031d58b99d515",
        "datetime": "1970-01-01T23:59:59+05:00"
    },
    "user": {
        "id": "1321545",
        "iin": "901020304050",
        "phone": "77771234567",
        "external_id": "abd41b46-8ad1-4109-9377-eede58ce7c69"
    },
    "operator": {
        "id": 123456,
        "username": "random_someone"
    },
    "status": "rejected",
    "tech_error_reason": null,
    "comment": "Причина отказа"
}
```

---

3) Тех. причина:

```
{
    "call": {
        "id": "6617af94da2031d58b99d515",
        "datetime": "1970-01-01T23:59:59+05:00"
    },
    "user": {
        "id": "1321545",
        "iin": "901020304050",
        "phone": "77771234567",
        "external_id": "abd41b46-8ad1-4109-9377-eede58ce7c69"
    },
    "operator": {
        "id": 123456,
        "username": "random_someone"
    },
    "status": "tech_error",
    "tech_error_reason": "Рандомная причина ошибки",
    "comment": null
}
```
