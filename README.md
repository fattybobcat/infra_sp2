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
  ```
    DB_ENGINE=django.db.backends.postgresql  # indicate that we are working with postgresql
    DB_NAME=postgres                         # database name
    POSTGRES_USER=login                      # login to connect to the database
    POSTGRES_PASSWORD=password               # password to connect to the database (set your own)
    DB_HOST=db                               # service (container) name
    DB_PORT=                                 # port for connecting to the database
    MAIL_SENDER=                             # mail for sending confirmation code
    PASSWORD_MAIL_SENDER=                    # password for mail
  ```
- Run in this directory:
    ```docker-compose up```
команду для создания суперпользователя,
команду для заполнения базы начальными даннымиdsd

