![yamdb_workflow](https://github.com/GlebMudrov/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

# CI/CD проекта Yamdb

### Описание проекта Yamdb:
Учебный проект, предназначенный для отработки навыков и применение теории при командной
разработки API для веб приложения YaMDb, базируемых на фреймворке Django и модуле Django Rest Framework.
Проект YaMDb собирает отзывы пользователей на произведения. Все произведения делятся на
категории («Книги», «Фильмы», «Музыка»). Произведению может быть присвоен жанр.
Добавлять произведения, категории и жанры может только администратор.
Добавлять отзывы, комментарии и ставить оценки могут только аутентифицированные пользователи.

### Технологии :
- Python
- Django
- Django REST Framework
- PostgreSQL
- Nginx
- Docker
- Git

### Запуск проекта:
Клонировать репозиторий (используем ssh) и перейти в него в командной строке:
```
git@github.com:GlebMudrov/yamdb_final.git
cd yamdb_final
```
Создание и запуск Docker-контейнеров:
```
sudo docker-compose up -d --build
```
Выполнить миграции, создать суперпользователя, собрать статику:
```
docker-compose exec web python manage.py makemigrations reviews
docker-compose exec web python manage.py makemigrations users
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --no-input
```

### Примеры использования API:
```
Детальное описание, алгоритм регистрации пользователей и примеры работы API 
проекта представлены в документации: http://localhost/redoc/ в формате ReDoc.
```

### Автор проекта:
Мудров Глеб