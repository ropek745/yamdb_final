![Yamdb_workflow](https://github.com/ropek745/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

Проект YaMDb, упакованный в Docker контейнеры
========================================================
Проект YaMDb собирает отзывы пользователей на произведения.
## Шаблон наполнения env-файла:
B_ENGINE=<тип БД>

DB_NAME=<имя базы данных>

POSTGRES_USER=<логин для подключения к базе данных>

POSTGRES_PASSWORD=<пароль для подключения к БД>

DB_HOST=<название сервиса (контейнера)>

DB_PORT=<порт для подключения к БД>
## Команды для запуска приложения в контейнерах ##
### 1. Склонировать репозиторий в рабочее пространство и перейти в нужную директорию: ###
```
git clone git@github.com:ropek745/infra_sp2.git
```
```
cd infra
```
### 2. Запустить сборку контейнеров docker-compose: ###
```
docker-compose up -d
```
### 3. Выполнить миграции: ###
```
docker-compose exec web python manage.py migrate
```
### 4. Создать суперпользователя: ###
```
docker-compose exec web python manage.py createsuperuser
```
### 5. Собрать статику: ###
```
docker-compose exec web python manage.py collectstatic --no-input
```
### 6. Заполнение базы данными: ###
```
docker-compose exec web python manage.py loaddata fixtures.json 
```

## Разработчик - [Роман Пекарев](https://github.com/ropek745) ##
