### Базовая информация

> POST /api/v2/userapi/user/list

### Параметры запроса

| Имя параметра | Тип  | Обязательно | Примечания       |
| :--------- | :-------- | :---- | :-------------------- |
| browserid | []string | Да | Список идентификаторов окон отпечатков пальцев браузера |

Вернуться к данным

```json
{
    "code":0,
    "msg":"Success",
    "data":{
        "apibrowser":[
            {
                "Name":"Test Window-1",
                "browserid":"23t87reotgjshgresogjhi49",
                "proxy":{
                    "type":"socks5",
                    "socks5":{
                        "Addr":"89.2.3.1",
                        "User":"admin",
                        "Passwd":"123456"
                    }
                },
                "accounts":{
                    "openurls":"www.baidu.com",
                    "groupid":"23984yoefjsoiroi4wqdfa",
                    "user":"admin",
                    "passwd":"adminrest",
                    "cookie":"erjagprtgjuwhgr;asgjresoi"
                }
            },
            {
                "Name":"Test Window-2",
                "browserid":"23t87reotgjsh3resogjhi49",
                "proxy":{
                    "type":"socks5",
                    "socks5":{
                        "Addr":"89.2.3.1",
                        "User":"admin",
                        "Passwd":"123456"
                    }
                },
                "accounts":{
                    "openurls":"www.baidu.com",
                    "groupid":"23984yoefjsoiroi4wqdfa",
                    "user":"admin",
                    "passwd":"adminrest",
                    "cookie":"erjagprtgjuwhgr;asgjresoi"
                }
            }
        ]
    }
}
```

| Имя параметра | Тип | Примечания                        |
| :-------- | :------ | :------------------------------------- |
| code     | int    | 0 Успех - 1 Ошибка формата ввода - 4 Ошибка входа в учетную запись |
| msg      | string | Возвращение сообщений об успехе или неудаче |

`apibrowser` Структурный массив：

| Имя параметра | Тип | Примечания                    |
| :--------- | :------ | :--------------------------------- |
| Name      | string | Имя браузера отпечатков пальцев |
| browserid | string | Изменить идентификатор окна браузера |
| proxy     | object | Информация о прокси (подробнее см. конфигурацию структуры "proxy") |
| accounts  | object | Подробнее см. конфигурацию структуры  'accounts' |

`proxy` конфигурация структуры：

| Имя параметра | Тип | Примечания                                               |
| :-------- | :------ | :------------------------------------------------------------ |
| type     | string | Тип прокси необязательно Official (куплен на нашем официальном сайте), self (уже в собственном списке прокси), socks5, http, https, local (локально) |
| socks5   | object | Агент socks5 (подробнее см. конфигурацию структуры "socks5") |

`socks5` конфигурация структуры：

| Имя параметра | Тип | Примечания |
| :-------- | :------ | :-------- |
| Addr     | string | Адрес агента |
| User     | string | Имя пользователя |
| Passwd   | string | Пароль |

`accounts` конфигурация структуры：

| Имя параметра | Тип | Примечания                |
| :-------- | :------ | :----------------------------- |
| openurls | string | Другие URL - адреса, к которым можно получить доступ при открытии браузера |
| groupid  | string | Группирование ID |
| user     | string | Счет Платформы        |
| passwd   | string | Пароль платформы      |
| cookie   | string | Счет или cookie не могут быть заполнены одновременно. |

