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

# Start locally

Use this command to start Geonode locally.

```sh
# Docker BUILD
docker-compose --env-file .env_dev_egis -f docker-compose.yml -f .\docker-compose.egis-local.prod.yml build

# Docker UP
docker-compose --env-file .env_dev_egis -f docker-compose.yml -f .\docker-compose.egis-local.prod.yml up -d

# Docker DOWN
docker-compose --env-file .env_dev_egis -f docker-compose.yml -f .\docker-compose.egis-local.prod.yml down
```

After running successfully, the service should be available at `http://localhost:8001/`.