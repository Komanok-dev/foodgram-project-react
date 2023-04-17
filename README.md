![Foodgram](https://github.com/Komanok-dev/foodgram-project-react/actions/workflows/foodgram_workflow.yml/badge.svg)
# Проект Foodgram
​
Проект Foodgram собирает рецепты пользователей. Пользователи могут публиковать рецепты, подписываться на публикации других пользователей, добавлять рецепты в избранное, а также скачивать список необходимых продуктов из рецепта для приготовления блюд.
​
Server address:  
[komanok.hopto.org](http://komanok.hopto.org/)

## Стек технологий: 
* Python3
* Django REST Framework
* Postgres
* Linux
* Docker
* Docker-compose
* Gunicorn
* Nginx
* Workflow
* Git
---

## Как запустить проект: 
​
**Клонировать репозиторий командой:**
```
git clone
```

**Создайте .env файл в директории infra/, в котором должны содержаться следующие переменные:**
```
SECRET_KEY='django-insecure-%2=o^w0(8hh&qk1fxv1*aj#a!+lydq$5-24*)y82j79y9bi#-k'
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
DB_HOST=db
DB_PORT=5432
Debug=False
```

**Занесите в раздел Secrets вашего Github указанные выше переменные, а также следующие:**
```
Ваш докерхаб:
DOCKER_USERNAME
DOCKER_PASSWORD

Ваш удаленный сервер:
HOST
USER
SSH_KEY
PASSPHRASE

По желанию можно включить оповещения в телеграм:
TELEGRAM_TO
TELEGRAM_TOKEN
```

**Cкопируйте на свой удаленный сервер файлы:**
```
infra/docker-compose.yml
infra/nginx.conf
и папку
docs/
командами:
scp infra/docker-compose.yml hostname@ip-adress:/home/username/
scp infra/nginx.conf hostname@ip-adress:/home/username/
scp -r docs hostname@ip-adress:/home/username/
```

**Сделайте commit и push проекта на github:**
```
git add .
git commit -m 'comment'
git push
```

**Cоздайте суперпользователя на сервере:**
```
docker-compose exec backend python manage.py createsuperuser
```
