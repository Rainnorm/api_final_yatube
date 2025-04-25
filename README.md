# api_final_yatube
### Описание проекта:

API для сервиса YATUBE. Позволяет получать список публикаций, комментариев, групп сервиса, создавать публикации и комментарии к постам, подписываться на других пользователей посредством API запросов. Безопасные запросы можно выполнять анонимно, для других запросов нужно получать токен.

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/Rainnorm/api_final_yatube
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python -m venv venv

```
или если установлено несколько версий Python
```
py -3.x -m venv venv
```
Где x - необходимая версия
```
source venv/Scripts/activate
```

Установить зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python manage.py migrate
```

Запустить проект:

```
python manage.py runserver
```

### Примеры использования:

Запрос на получение токена:

```
POST /api/v1/jwt/create/
{
  "username": "string",
  "password": "string"
}
```

Получение публикаций:

```
GET /api/v1/posts/
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
```

Создание публикации:

```
POST /api/v1/posts/
{
  "text": "string",
  "image": "string",
  "group": 0
}
```

Для просмотра других примеров и более подробного руководство после запуска проекта на локальной машине перейдите:

```
http://127.0.0.1:8000/redoc/
```
