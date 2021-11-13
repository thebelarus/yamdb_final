# Описание проекта YaMDb

Проект YaMDb собирает отзывы (Review) пользователей на произведения (Titles). Произведения делятся на категории: «Книги», «Фильмы», «Музыка». Список категорий (Category) может быть расширен администратором (например, можно добавить категорию «Изобразительное искусство» или «Ювелирка»).

В каждой категории есть произведения: книги, фильмы или музыка. Например, в категории «Книги» могут быть произведения «Винни-Пух и все-все-все» и «Марсианские хроники», а в категории «Музыка» — песня «Давеча» группы «Насекомые» и вторая сюита Баха.
Произведению может быть присвоен жанр (Genre) из списка предустановленных (например, «Сказка», «Рок» или «Артхаус»). Новые жанры может создавать только администратор.

Благодарные или возмущённые пользователи оставляют к произведениям текстовые отзывы (Review) и ставят произведению оценку в диапазоне от одного до десяти (целое число); из пользовательских оценок формируется усреднённая оценка произведения — рейтинг (целое число). На одно произведение пользователь может оставить только один отзыв.

## Технологии:
Django
Django REST Framework
Django REST Framework Simplejwt

## Установка:

Клонировать репозиторий и перейти в него в командной строке:

```bash
git clone https://github.com/uprofound/api_yamdb.git
```

```bash
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

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

### Создание суперпользователя

Для администрирования проекта и создания категорий, жанров и т.д. используется суперпользователь. Для его создания выполните команду:

```bash
python3 manage.py createsuperuser
```

### Импорт данных

В проекте есть возможность загружать данные из csv-файлов в директории api_yamdb/static/data.  
Для загрузки в БД данных из файла filename.csv выполните команду:

```bash
python3 manage.py import filename
```

Для загрузки в БД данных из всех файлов сразу выполните команду:

```bash
python3 manage.py import all
```

### Импорт данных из файла фикстур fixtures.json
```bash
docker-compose exec web python manage.py loaddata fixtures.json
```

### Пример файла env для настройки базы данных в проекте Django
```bash
# Движок базы данных
DB_ENGINE=django.db.backends.postgresql
# Имая базы данных
DB_NAME=postgres
# Имя пользователя базы данных
POSTGRES_USER=postgres
# Пароль пользователя базы данных
POSTGRES_PASSWORD=postgres
# Адрес базы данных
DB_HOST=db
# Порт базы данных
DB_PORT=5432 
# Секретный ключ проекта Django
SECRET_KEY='p&l%385148kslhtyn^##a1)ilz@4zqj=rq&agdol^##zgl9(vs'
```

### Команды для для запуска приложения в контейнере
```bash
# Запуск проекта 
docker-compose up
# Остановка проекта 
docker-compose down
# Запуск и сборка проекта после внесения изменений
docker-compose up --build
# Вполнить команду command в выполняющемся контейнере service name
docker-compose exec [service name] [command]
```
![example workflow](https://github.com/thebelarus/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)