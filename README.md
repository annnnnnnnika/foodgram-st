# Foodgram — Продуктовый помощник

Из задания: Вам предстоит поработать с проектом «Фудграм» — сайтом, на котором пользователи будут публиковать свои рецепты, добавлять чужие рецепты в избранное и подписываться на публикации других авторов. Зарегистрированным пользователям также будет доступен сервис «Список покупок». Он позволит создавать список продуктов, которые нужно купить для приготовления выбранных блюд.
## Возможности

- Регистрация и авторизация пользователей
- Публикация рецептов с изображениями
- Добавление тегов и ингредиентов
- Фильтрация рецептов по тегам
- Добавление рецептов в избранное
- Формирование списка покупок
- Админ-панель

---

## Стек технологий

* Python 3.13
* Django 5.2
* Django REST Framework
* PostgreSQL
* Docker
* Docker Compose
* Nginx
* Gunicorn
* GitHub Actions

## Запуск с Docker

### 1. Клонирование репозитория

```bash
git clone https://github.com/annnnnnnnika/foodgram-st.git
cd foodgram-st
```

### 2. Создание и настройка `.env` файла

В корне проекта создайте файл `.env` со следующим содержимым:

```env
DEBUG=True
SECRET_KEY=django-insecure-123
ALLOWED_HOSTS=127.0.0.1,localhost,backend
POSTGRES_DB=django_db
POSTGRES_USER=django_user
POSTGRES_PASSWORD=django_password
DB_HOST=db
DB_PORT=5432
```

### 3. Сборка и запуск контейнеров

Перейдите в директорию `infra/` и выполните:

```bash
docker-compose up -d --build
```

### 4. Применение миграций и сбор статики

```bash
docker exec foodgram_back python manage.py makemigrations users

docker exec foodgram_back python manage.py makemigrations recipes

docker-compose exec backend python manage.py migrate

docker-compose exec backend python manage.py collectstatic --noinput
```

### 5. Создание суперпользователя

```bash
docker-compose exec backend python manage.py createsuperuser
```


### 7. Доступ к приложению

* Фронтенд: [http://localhost/](http://localhost/)
* Админ-зона: [http://localhost/admin/](http://localhost/admin/)
* API: [http://localhost/api/](http://localhost/api/)

## Автор

**Жилина Анна Виктория**

## Ссылка на GitHub

https://github.com/annnnnnnnika
