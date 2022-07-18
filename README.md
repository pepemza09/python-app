# python-app
This is the template to develop projects with Django using docker

## To start a new project 🔧
- Clone the repository into a local directory
- Type on te current directory (where the project was clone)
```sh
# in this case the name of the project is "app"

docker-compose run --rm app sh -c "django-admin startproject app ."
```
## To start a new python app 🔧
- to start a new app (i.e. core) type
```sh
docker-compose run --rm app sh -c "python manage.py startapp core"
```
when setup is finish, add the app in the project editing the INSTALLED_APPS on app/app/settings.py

- to create migrations
```sh
docker-compose run --rm app sh -c "python manage.py makemigrations"
```
- to create super user
```sh
docker-compose run --rm app sh -c "python manage.py createsuperuser"
```
- to production don't forget make copy the .env.sample on .env file
```sh
cp .env.sample to .env
```
## Running the server on test/dev mode 🔧
```sh
docker-compose -f .\docker-compose.yml down --volumes
docker-compose -f docker-compose.yml build
docker-compose -f docker-compose.yml up
```
## Running the server on production mode 🔧
This config run the nginx server with the app inside

```sh
docker-compose -f .\docker-compose-deploy.yml down --volumes
docker-compose -f docker-compose-deploy.yml build
docker-compose -f docker-compose-deploy.yml up
```
