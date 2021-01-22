# YamDB

API-project running across multiple Docker containers.
YamDB allows you to leave reviews, ratings and comments on creation


## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.
See deployment for notes on how to deploy the project on a live system.

### Prerequisites

* Download [Docker Desktop](https://www.docker.com/products/docker-desktop) for Mac or Windows. [Docker Compose](https://docs.docker.com/compose/) will be automatically installed. On Linux, make sure you have the latest version of [Compose](https://docs.docker.com/compose/install/).
* Create your own mail for the project, which will send a verification code to confirm users (Better gmail) 

### Containers

The stack uses Python and Postgres for storage.

## INSTALLATION

- Copy this repository to your local machine;
- Create `.env` file with the following constants:
    `DB_ENGINE=django.db.backends.postgresql'
    `'DB_NAME=postgres`
      POSTGRES_USER=postgres # логин для подключения к базе данных
      POSTGRES_PASSWORD=postgres1 # пароль для подключения к БД (установите свой)
      DB_HOST=db # название сервиса (контейнера)
      DB_PORT=   # порт для подключения к БД
      MAIL_SENDER=
      PASSWORD_MAIL_SENDER=                                    
  '''

команду для создания суперпользователя,
команду для заполнения базы начальными даннымиdsd

