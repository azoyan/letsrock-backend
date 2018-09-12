# letsrock-backend

## API
Запросы к серверу по HTTP

Тип запроса `POST`

`Content-Type: application/json`

### Регистрация
`http://loocalhost:57805/api/register`
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

### Авторизация.
`http://localhost:57805/api/auth`

```JSON
{
  "Identity": "mymail@ya.ru",
  "Password": "Qwerty1234_"
}
```

Ответ:
```JSON
{
    "code": 0,
    "message": "Успешная авторизация",
    "token": null,
    "userId": 1
}
```
