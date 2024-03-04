# How to use it
  - Start docker desktop
  - Clone the repository in your local machine by typing ```git clone link```
  - cd into the project
  - Run ```docker volume create volume_name``` to create a docker volume in your machine. Change the volume_name in docker_compose.yml file according to your need
  - Create a .env file and store credentials.
```
MYSQL_HOST=mysql
MYSQL_USER=root
MYSQL_PASSWORD=Describly&123
MYSQL_DB=fastapi
MYSQL_PORT=3306
```
You do not need to change anything here, but if you would like to change the username, password or database name, you can modify it at this point in the .env file attached to this project.
# Building the project
 - We can start building our project by running ```docker-compose build```
 - once build is completed, run ```docker-compose up``` to start the services. Leave the terminal open to check the logs
 - To stop the services you can press ```ctrl+c```

# Commands
   - To generate migration from model
 ```docker-compose run fastapi-service /bin/sh -c "alembic revision --autogenerate -m "create my table table""```\n
   - To aplly the migration to database
 ```docker-compose run fastapi-service /bin/sh -c "alembic upgrade head"``` \n
   - To revert last applied migration
 ```docker-compose run fastapi-service /bin/sh -c "alembic downgrade -1"``` \n
