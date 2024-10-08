### Базовая информация

> POST /api/v2/userapi/selfproxy/list

### Параметры запроса

| Имя параметра | Тип | Обязательно | Примечания |
| :-------- | :----- | :--- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| page | int | Да | Стр        |
| pageSize    | int | Да | Размер страницы |
| name    | string | Нет | Имя агента |


Примеры

```json
const requestBody = {
    "page": 1,
    "pageSize": 10,
    "name": ""
};
```

Вернуться к данным

```json
{
    "code": 0,
    "msg": "Success",
    "data": {
        "list": [
            {
                "deviceid": "cc12c5e1663e3efcb05e66088XX",
                "companyid": "e9b455594c05b52210226XX",
                "name": "Изменение прокси",
                "proxyaddr": "1.1.1.1:2333",
                "proxytype": 1,
                "user": "99999",
                "passwd": "55555",
                "notes": "прокси 1",
                "createdat": "2024-04-12 15:58:06"
            }
        ],
        "total": 1,
        "pageSize": 10,
        "currentPage": 1
    }
}
```

| Имя параметра | Тип | Примечания                                                    |
| :------- | :----- | :---------------------------------------------------------------- |
| code     | int    | 0 Успех - 1 Ошибка формата ввода - 2 Сервисная аномалия - 4 Аномалия входа в учетную запись |
| msg      | string | Возвращение сообщений об успехе или неудаче   |
| deviceid      | string | Агент id |
| companyid      | string | Командыid |
| name      | string |  Имя агента  |
| proxytype | int | Тип прокси 1: пароль с именем пользователя sock5 протокол 3: пароль без имени пользователя протокол socks5 протокол 4: http протокол 5: https протокол 6: http протокол с именем пользователя протокол с паролем 7: https протокол с именем пользователя |
| proxyaddr | string | Адрес агента |
| user    | string | Номер учётной записи |
| passwd    | string |  Пароль входа |
| notes    | string |  Примечания     |
| createdat    | string | Время создания |

