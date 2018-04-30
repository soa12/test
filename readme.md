# Регистрация/Авторизация

||Метод |Описание  |
|--|--|--|
|**post**|  /register|  Регистрация нового пользователя|
|**post**|  /login| Авторизация 
 
### /register
#### Пример запроса
    {
    	"name":"name",
    	"login":"login@domain.com",
    	"password":"passwd12"
    }
**name**
- любые последовательность символов длиной до 20 
**login**
- до знака @ до 20 латинских символов
- после знака @ корректный домен
**password** 
- любая последовальность символов длиной от 8 до 20
- обязательно наличие букв и цифр

#### Пример ответа
    {
    	"status":"200",
    	"response":"login@domain.com"
    }

#### Коды ошибок
400 - Пользователь с таким логином уже зарегистрирован
### /login
#### Пример запроса
    {
    	"login":"login@domain.com",
    	"password":"passwd12"
    }
#### Ответ
    {
    	"status":"200",
    	"response":"login@domain.com"
    }
#### Коды ошибок
400 - Пользователь не найден. Проверьте правильность введенных данных.
# Работа с документом
||Метод |Описание  |
|--|--|--|
|**post**|  /upload| Загрузка документа для заверение|
|**post**|  /check| Проверка документа на валидность 

### /upload
#### Пример запроса
    {
    	"hash":"46ca5f6e0b40078d02ec5efd36df31ddb34586a37481a12f568c126068113ff5",
    	"date":"2018-01-01 01:00:00",
    	"name":"document"
    }
**hash**
- sha256
**date**
- формат: гггг-мм-дд чч:мм:сс
**name**
- любая последовательность символов длиной до 30
#### Ответ
    {
    	"status": "success",
    	"bitcoinAdrr": "d0af4979b9797ef646fd5b75c3224649",
    	"ethereumAddr": "d0af4979b9797ef646fd5b75c3224649"
    }
#### Коды ошибок

### /check
#### Пример запроса

#### Ответ

#### Коды ошибок
