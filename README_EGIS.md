# Load GIT repository

Load GIT repository
```sh
# Clone repository
git clone https://github.com/phardy-egis/django-geonode-dev.git

# Checkout branch
git checkout 4.0.x-egis

# Load submodules
git submodule init
git submodule update

```

# Start locally in "production" mode

Use this command to start Geonode locally with all the features as it was in production.

```sh
# Docker BUILD
docker-compose --env-file .env_dev_egis -f docker-compose.yml -f .\docker-compose.egis-local.prod.yml build

# Docker UP
docker-compose --env-file .env_dev_egis -f docker-compose.yml -f .\docker-compose.egis-local.prod.yml up -d

# Docker DOWN
docker-compose --env-file .env_dev_egis -f docker-compose.yml -f .\docker-compose.egis-local.prod.yml down
```

After running successfully, the service should be available at `http://localhost:8001/`.


# Start locally in development mode

Use this command to start Geonode locally with all the features as it was in development.

```sh
# Docker BUILD
docker-compose --env-file .env_dev_egis -f docker-compose.yml -f .\docker-compose.egis-local.dev.yml build

# Docker UP
docker-compose --env-file .env_dev_egis -f docker-compose.yml -f .\docker-compose.egis-local.dev.yml up -d

# Enter django container shell
docker exec -it django4geonode /bin/bash

# Start Django server in development mode
python manage.py runserver 0.0.0.0:8001
```

After running successfully, the service should be available at `http://localhost:8001/`.

In this mode:
- Django listen for file changes
- PostgreSQL database becomes availble on port 35432

