# django-app
Django app template with docker

# start a new project
- Type on te current directory (where the project was clone)

docker-compose run --rm app sh -c "django-admin startproject app ."

- to start a new app (i.e. core) type

docker-compose run --rm app sh -c "python manage.py startapp core"

when setup is finish, add the app in the project editing the INSTALLED_APPS on app/app/settings.py

- to create migrations
docker-compose run --rm app sh -c "python manage.py makemigrations"

- to create super user
docker-compose run --rm app sh -c "python manage.py createsuperuser"

- to production don't forget:

rename .env.sample to .env


docker-compose -f .\docker-compose-deploy.yml down --volumes
docker-compose -f docker-compose-deploy.yml build
docker-compose -f docker-compose-deploy.yml up
