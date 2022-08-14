# Описание

Проект - реализация API для проекта yatube.

Ключевые моменты:

Применены вьюсеты.

Для аутентификации использованы JWT-токены.

У неаутентифицированных пользователей доступ к API только на чтение (Исключение — эндпоинт /follow/). Аутентифицированным пользователям разрешено изменение и удаление своего контента.

# Установка

## 1) Клонировать репозиторий и перейти в него в командной строке
```
git clone [git@github.com:fukyduky/api_final_yatube.git](https://github.com/fukyduky/api_final_yatube.git)

yatube_api
```

## 2) Создать и активировать виртуальное окружение для проекта
```
python -m venv venv

. venv/scripts/activate
```
## 3) Установить зависимости
```
python pip install -r requirements.txt
```
## 4) Сделать миграции
```
python manage.py makemigrations
python manage.py migrate
```
## 5) Запустить сервер
```
python manage.py runserver
```

# Примеры запросов

## Get-запрос к объекту

### Запрос

`GET /api/v1/posts/`

### Ответ

    {
  "count": 123,
  "next": "http://api.example.org/accounts/?offset=400&limit=100",
  "previous": "http://api.example.org/accounts/?offset=200&limit=100",
  "results": [
    {
      "id": 0,
      "author": "string",
      "text": "string",
      "pub_date": "2021-10-14T20:41:29.648Z",
      "image": "string",
      "group": 0
    }
  ]
}

## POST-запрос

### Запрос

`POST /api/v1/posts/{post_id}/comments/)/`

### Ответ

    {
  "id": 0,
  "author": "string",
  "text": "string",
  "created": "2019-08-24T14:15:22Z",
  "post": 0
    }

## GET-запрос к несуществующему объекту

### Запрос

`GET /api/v1/groups/{id}/)`

### Ответ

    {
  "detail": "Страница не найдена."
    }
    
## Изменение объекта

### Запрос

`PUT /api/v1/posts/{post_id}/comments/{id}/`

### Ответ

    {
  "id": 0,
  "author": "string",
  "text": "string",
  "created": "2019-08-24T14:15:22Z",
  "post": 0
}
