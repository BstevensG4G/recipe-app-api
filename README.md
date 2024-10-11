# Recipe App API - README

# Recipe App API

## Prerequisites

- Docker
- Docker Compose
- Git

## Getting Started

### Clone the Repository

```bash
git clone https://github.com/BstevensG4G/recipe-app-api.git
cd recipe-app-api
```

### Build and Run the Project

```bash
docker compose up --build
```
### Create SuperUser

```bash
docker compose run --rm app sh -c "python manage.py create superuser"
```
### Login to Admin Portal http://localhost:8000/admin/


## Development

### Check Formatting

To check the code formatting, run:

```bash
docker compose run --rm app sh -c "flake8"
```

### Run Tests

To run the tests, use the following command:
Utilizes /core/management/commands/wait_for_db to ensure DB is running because
DB temp table is used in tests.
```bash
docker compose run --rm app sh -c "python manage.py wait_for_db && python manage.py test"
```

### Make Migrations

To create new migrations:
Utilizes /core/management/commands/wait_for_db to ensure DB is running because
DB temp table is used in tests.
```bash
docker compose run --rm app sh -c "python manage.py wait_for_db && python manage.py makemigrations"
```

### Apply Migrations

To apply migrations and update the database schema:
Utilizes /core/management/commands/wait_for_db to ensure DB is running because
DB temp table is used in tests.
```bash
docker compose run --rm app sh -c "python manage.py wait_for_db && python manage.py migrate"
```

## Additional Information

### API endpoints
See the swagger portal after setting up the project at this url:
http://localhost:8000/api/docs


For more details about the project structure, configuration, please refer to the project documentation.