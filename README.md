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
    ``` 
    docker-compose up
    ```
- Great! Server is running!

### Database setup

There is no data in our database now. Need to install migrations and write test database

1. Open a new terminal and run:
```
  docker container ls
```
  You will see next (example):
```
CONTAINER ID   IMAGE                     COMMAND                  CREATED          STATUS          PORTS                    NAMES
f19f76f82f0c   fattybobcat/yamdb:v1.12   "gunicorn api_yamdb.…"   47 seconds ago   Up 46 seconds   0.0.0.0:8000->8000/tcp   infra_sp2_web_1
b93f460c8dbb   postgres:12.4             "docker-entrypoint.s…"   47 seconds ago   Up 46 seconds   5432/tcp                 infra_sp2_db_1
```
2. Go to the directory where the given project is stored and run the following command to copy the database dump fixture.json to the project:
  ```
  docker cp  fixture.json <CONTAINER ID>:/
  ```
3. To enter the web container (fattybobcat/yamdb:v1.12): run `docker exec -it <CONTAINER ID> bash`
4. Make migrate `python manage.py migrate`
5. To load the database run the commands:
```
  python3 manage.py shell
# execute in the opened terminal:
>>> from django.contrib.contenttypes.models import ContentType
>>> ContentType.objects.all (). Delete ()
>>> quit ()

python manage.py loaddata dump.json
```

### Create superuser:

1. To enter the web container (fattybobcat/yamdb:v1.12): run `docker exec -it <CONTAINER ID> bash`
2. Run the commands: `python manage.py createsuperuser`

## Basic description api requests:
  [redoc]()
