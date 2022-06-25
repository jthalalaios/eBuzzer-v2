# eBuzzer-v2

This is a refactor of eBuzzer project with Docker (stack) and with frameworks (laravel for the api and vue for the fronted).
Moreover, it will include extra features (i will add the list when whole project is done).


# ebuzzer-v2-stack

Before you start building the docker stack:

1) rename all .env-example to .env

Docker stack info:

1) Create a docker image with the following command: docker build -t ebuzzer-api

2) Change the .env-example outside the laravel folder (ebuzzer-backend parent folder) the ports number that you want to use and rename it to .env

3) Build the the docker image: docker-compose build --no-cache

4) Up the containers: docker-compose up -d

Laravel settings:

1) Change the .env-example settings inside the laravel folder that you want to use and rename it to .env

2) You have to put settings for mailer smtp on laravel at .env (inside laravel folder) on creating user and for the forgot password, else it will output 500 server error because when user's is creating , an email verification goes to the user's email (same with forgot password).

After docker's containers are up:

1) Go inside ebuzzer-api container with the following command: docker exec -it ebuzzer-api bash

2) Run migrate: php artisan migrate

3) Run seeder: php artisan db:seed --class=DatabaseSeeder

4) In case that key is not on .env inside laravel's folder use the command: php artisan key:generate (to set the the APP_KEY value in your .env)

