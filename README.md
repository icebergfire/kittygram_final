# Kittygram — социальная сеть для обмена фотографиями котиков

## Описание проекта

Kittygram — это веб-приложение, в котором пользователи могут регистрироваться, загружать фотографии своих котиков с описанием их достижений и просматривать котиков других пользователей. Проект состоит из бэкенда на Django REST Framework, фронтенда на React и использует PostgreSQL в качестве базы данных.

### Возможности

- Регистрация и аутентификация пользователей
- Добавление, редактирование и удаление карточек котиков
- Загрузка фотографий котиков
- Указание породы, цвета и достижений котика
- Просмотр карточек других пользователей

## Стек технологий

- **Backend**: Python 3.9, Django 3.2, Django REST Framework 3.12, Djoser
- **Frontend**: React, JavaScript, Node.js 18
- **Database**: PostgreSQL 13
- **Web Server**: Nginx 1.22
- **WSGI Server**: Gunicorn 20.1
- **Контейнеризация**: Docker, Docker Compose
- **CI/CD**: GitHub Actions
- **Хранение образов**: Docker Hub

## Как развернуть проект

### Предварительные требования

- Docker и Docker Compose установлены на сервере
- Аккаунт на [Docker Hub](https://hub.docker.com/)

### Локальный запуск

1. Клонируйте репозиторий:

```bash
git clone git@github.com:<username>/kittygram_final.git
cd kittygram_final
```

2. Создайте файл `.env` в корне проекта на основе `.env.example`:

```bash
cp .env.example .env
```

3. Заполните переменные окружения в файле `.env`:

```
POSTGRES_DB=kittygram           # имя базы данных
POSTGRES_USER=kittygram_user    # логин для подключения к БД
POSTGRES_PASSWORD=your_password # пароль для подключения к БД
SECRET_KEY=your_secret_key      # секретный ключ Django
DEBUG=False                     # режим отладки (True/False)
ALLOWED_HOSTS=127.0.0.1,localhost  # разрешённые хосты
DB_HOST=db                      # имя контейнера БД
DB_PORT=5432                    # порт БД
DOCKERHUB_USERNAME=your_login   # ваш логин на Docker Hub
```

4. Запустите проект:

```bash
docker compose up -d
```

5. Проект будет доступен по адресу: `http://localhost:9001`

### Деплой на сервер

Проект автоматически деплоится при пуше в ветку `main` через GitHub Actions. Для этого необходимо настроить секреты в настройках репозитория на GitHub:

- `DOCKERHUB_USERNAME` — логин на Docker Hub
- `DOCKERHUB_TOKEN` — токен Docker Hub
- `HOST` — IP-адрес сервера
- `USER` — имя пользователя на сервере
- `SSH_KEY` — SSH-ключ для доступа к серверу
- `SSH_PASSPHRASE` — пароль от SSH-ключа
- `POSTGRES_DB`, `POSTGRES_USER`, `POSTGRES_PASSWORD` — настройки БД
- `SECRET_KEY` — секретный ключ Django
- `ALLOWED_HOSTS` — разрешённые хосты
- `TELEGRAM_TO` — ID чата в Telegram для уведомлений
- `TELEGRAM_TOKEN` — токен Telegram-бота

## Автор

Студент Яндекс Практикум
