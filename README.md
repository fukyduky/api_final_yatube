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
