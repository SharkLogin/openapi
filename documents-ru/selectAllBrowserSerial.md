### Базовая информация

> POST /api/v2/userapi/user/shopseriallist

Вернуться к данным

```json
{
    "code": 0,
    "msg": "Success",
    "data": {
        "list": [
            {
                "shopId": "b2a354395c06b5e16e",
                "serial": 96
            },
            {
                "shopId": "ebf96c272b708c944ef1a16",
                "serial": 89
            },
            {
                "shopId": "e7fd6d69588b5de2dffdd3f2",
                "serial": 88
            },
            {
                "shopId": "d4a41c1f5329addd406c5b4",
                "serial": 10
            }
        ]
    }
}
```

| Имя параметра | Тип | Примечания                        |
| :-------- | :------ | :------------------------------------- |
| code     | int    | Примечание 0 Успех - 1 Ошибка формата ввода - 2 Аномалия запроса - 4 Аномалия входа в учетную запись |
| msg      | string | Возвращение сообщений об успехе или неудаче |
| shopId      | string | Обратная среда id |
| serial      | int | Возвращает серийный номер среды |

