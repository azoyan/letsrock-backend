# letsrock-backend

## API
Запросы к серверу по HTTP

Тип запроса `POST`

`Content-Type: application/json`

### Регистрация
Тело запроса:
```JSON
{
    "FirstName": "Petr",
    "LastName": "Petrov",
    "Nickname": "Petya",
    "Phone": "+79182572012",
    "Email": "mymail@ya.ru",
    "PhotoB64": null,
    "Password":"Qwerty1234_"
}
```

Ответ:
```JSON
{
    "code": 8,
    "message": "Email уже занят"
}
```
