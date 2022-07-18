# python-app
This is the template to devel projects with Django using docker

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
