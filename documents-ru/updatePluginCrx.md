### Базовая информация

> PUT /api/v2/plugin/open/updatePluginCrx

Описание интерфейса: Изменить форму плагина, запрос Body Application/json

### Параметры запроса

```json
{
  "name": "",
  "icon": "",
  "file": "",
  "brief": "",
  "uuid": "",
  "pluginId": "",
  "imgs": []
}
```

|Имя параметра|Тип|Обязательно|Примечания|
|:----| :-- | :-- | :--- |
| pluginId | string | Да | Идентификатор модуля |
| name | string | Да | Имя |
| icon | string | Нет | Значок |
| file | string | Нет | Адрес файла |
| brief | string | Нет | Введение |
| uuid | string | Нет | Уникальный идентификатор модуля Chrome |
| imgs | []string | Нет | Карта сева |

Успешное осуществление

```json
{
  "code": 200,
  "data": "",
  "msg": "Операция прошла успешно",
  "requestId": ""
}
```

Ошибка выполнения

```json
{
  "code": 30008,
  "data": {},
  "msg": "Ошибка получения",
  "requestId": ""
}
```

