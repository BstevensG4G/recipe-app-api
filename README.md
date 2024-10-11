# recipe-app-api
Working through an advanced tutorial by Mark Winterbottom titled, "Build a Backend REST API with Python & Django - Advanced"

## Setting Up
Designed to run inside a docker container using `docker compose`

```sh
$ git clone https://github.com/BstevensG4G/recipe-app-api.git
$ cd recipe-app-api
```
The dependencies are restored within the docker container
Changing the `ARG DEV=true` to false will modify requirements to be installed for production.

### In development formatting can be checked using Flake8-Django package v1.4
```sh
docker compose run --rm app sh -c "flake8"
```

### Tests can be run with the following command
`wait_for_db` is a script that checks for db availability prior to running tests
```sh
$ docker-compose run --rm app sh -c "python manage.py wait_for_db && python manage.py test"
```

## Notable Django default modifications
Customization of Django built-in User model is modified to make email the default
