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

### Авторизация
Для авторизации в заголовке HTTP-запроса, указываем куки присланные нам при регистрации.
```HTTP
POST / HTTP/1.1
Host: localhost:57805
Content-Type: application/json
Cookies: CfDJ8E4mTHEq1xxNvaAnWFxPBVwG6hI-GcdKfQVbnW8pMKfOS7N3Z2LYpWoGAuILqvepuBX2ldaNdc1gcDxVzXBpDp6DFmZ0LA8uf1by5PagLF0jzlTZ8q7xSUYp4GIYt2Mp4FjAqvDnr6gkM4TwaSruF24Vk-ffgSBPAzS6B08IN5B2RrCXanyIz132kl8MKtaOxMps84ZAHydRgyWWZCANuFIF-JSfCQ629GKmGQWGd3vPcVGMEkaoDOlx0QOc0--kZQE9_zjGXnFIziSc7k64P2IKiNk2mnN5WV5A4Gj0fKMFY81BFoc7guxEMl9aFC3FDUaRcLp6-2zHbW9RY7sCbSlp_1SdU-9Z
```

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

### Получение информации о пользователе
```HTTP
POST / HTTP/1.1
Host: localhost:57805
Cookies: CfDJ8E4mTHEq1xxNvaAnWFxPBVwG6hI-GcdKfQVbnW8pMKfOS7N3Z2LYpWoGAuILqvepuBX2ldaNdc1gcDxVzXBpDp6DFmZ0LA8uf1by5PagLF0jzlTZ8q7xSUYp4GIYt2Mp4FjAqvDnr6gkM4TwaSruF24Vk-ffgSBPAzS6B08IN5B2RrCXanyIz132kl8MKtaOxMps84ZAHydRgyWWZCANuFIF-JSfCQ629GKmGQWGd3vPcVGMEkaoDOlx0QOc0--kZQE9_zjGXnFIziSc7k64P2IKiNk2mnN5WV5A4Gj0fKMFY81BFoc7guxEMl9aFC3FDUaRcLp6-2zHbW9RY7sCbSlp_1SdU-9Z
```
`http://localhost:57805/api/GetUserInfo`

Ответ:
```JSON
{
    "code": 41,
    "message": "Успех",
    "info": {
        "id": 1,
        "firstname": "Petr",
        "lastname": "Petrov",
        "email": "mymail@ya.ru",
        "phone": "+79182572012",
        "bands": null
    }
}
```
