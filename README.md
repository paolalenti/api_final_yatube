#  API для социальной сети Yatube

## Описание
REST API для социальной сети блогов с возможностью:
- Публикации постов
- Комментирования записей
- Подписки на авторов
- Группировки постов по темам
- Аутентификации через JWT-токены

## Установка

Клонировать репозиторий и перейти в него в командной строке:
```bash
git clone https://github.com/yandex-praktikum/kittygram.git
```
```bash
cd kittygram
```
Создать и активировать виртуальное окружение:

```bash
python3 -m venv env
```
```bash
source env/bin/activate
```
Установить зависимости из файла requirements.txt:
```bash
python3 -m pip install --upgrade pip
```
```bash
pip install -r requirements.txt
```
Выполнить миграции:
```bash
python3 manage.py migrate
```
Запустить проект:
```bash
python3 manage.py runserver
```

## Примеры
Получение токена

POST http://127.0.0.1:8000/api/v1/jwt/create/
Content-Type: application/json
```json
{
    "username": "your_username",
    "password": "your_password"
}
```

Подписка на автора

POST http://127.0.0.1:8000/api/v1/follow/
Authorization: Bearer <your_access_token>
Content-Type: application/json
```json 
{
    "following": "author_username"
}
```

Получение комментариев

GET http://127.0.0.1:8000/api/v1/posts/1/comments/

По адресу http://127.0.0.1:8000/redoc/ будет доступна документация для API Yatube. В документации описано, как работает API. Документация представлена в формате Redoc.