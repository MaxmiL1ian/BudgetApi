# BudgetApi
API реализует возможности учёта расходов/доходов конкретного пользователя 

## Запросы 

### Пользователь
GET api/v1/user/ - Аутентификация 
  
  Параметры: 
  + login 
  + password

POST api/v1/user/ - Регистрация 
 
  Параметры:  
  + first_name 
  + last_name 
  + login 
  + password

### Расходы
GET api/v1/expense/ - Получение записи
  
  Параметры: 
  + user_id

POST api/v1/expense/ - Добавление записи

  Параметры:  
  + user_id
  + comment 
  + amount
  + password

DELETE api/v1/expense/<int:pk>/ - Удаление записи

  Параметры:  
  + user_id 
  + id(записи)

### Доходы
GET api/v1/income/ - Получение записи

  Параметры: 
  + user_id
  
POST api/v1/income/ - Добавление записи

  Параметры:  
  + user_id
  + comment 
  + amount
  + password

DELETE api/v1/income/<int:pk>/ - Удаление записи

  Параметры:  
  + user_id 
  + id(записи) 

### Остаток
GET api/v1/income/ - Получение записи

  Параметры: 
  + user_id
## Тело запроса 

``` python
    url = ...api/v1/user/

    payload = json.dumps({
        "login": login,
        "password": password,
    })
    headers = {
        'Content-Type': 'application/json'
    }

    response = get(url=url, headers=headers, data=payload)
```
