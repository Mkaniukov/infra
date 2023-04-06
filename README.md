Проект YaMDb собирает отзывы (Review) пользователей на произведения (Title). Произведения делятся на категории: "Книги", "Фильмы", "Музыка". Список категорий (Category) может быть расширен.
Сами произведения в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.
В каждой категории есть произведения: книги, фильмы или музыка. Например, в категории "Книги" могут быть произведения "Винни Пух и все-все-все" и "Марсианские хроники", а в категории "Музыка" — песня "Давеча" группы "Насекомые" и вторая сюита Баха. Произведению может быть присвоен жанр из списка предустановленных (например, "Сказка", "Рок" или "Артхаус"). Новые жанры может создавать только администратор.
Благодарные или возмущённые читатели оставляют к произведениям текстовые отзывы (Review) и выставляют произведению рейтинг.

## Technologies

- Python 3
- Django REST Framework
- SQLlite
- Simple-JWT
- PostreSQL
- Nginx
- gunicorn
- Docker
- DockerHub
- GitHub Actions (CI/CD)

## Installation and launch

Clone repository and navigate to folder on command line::

```
git clone git@github.com:Mkaniukov/api_yamdb.git
```

```
cd api_yamdb
```

Create and activate virtual environment:

```bash 
cd infra

touch .env
```
```

```bash 
echo DB_ENGINE=django.db.backends.postgresql >> .env

echo DB_NAME=postgres l >> .env

echo POSTGRES_PASSWORD=postgres >> .env

echo POSTGRES_USER=postgres  >> .env

echo DB_HOST=db  >> .env

echo DB_PORT=5432  >> .env
```
```bash 
docker-compose exec web python manage.py migrate

docker-compose exec web python manage.py createsuperuser

docker-compose exec web python manage.py collectstatic --no-input 

docker-compose exec web python manage.py loaddata fixtures.json
```
python3 manage.py runserver
```

[ReDoc](http://127.0.0.1:8000/redoc/)

## The authors:
Murat Kaniukov
Sergey Sarimov
Andrey Ignatev
