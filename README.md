## Hybrid NAS server configuration
[![Docker Compose Check](https://github.com/peplxx/nas-setup/actions/workflows/compose-check.yaml/badge.svg)](https://github.com/peplxx/nas-setup/actions/workflows/compose-check.yaml)

### Overview
A Hybrid NAS (Network-Attached Storage) server combines the capabilities of traditional NAS with the features of cloud storage. 

### Containers
- **Nextcloud**: File sync, calendars, and contacts.
- **MariaDB**: Database backend.
- **Nginx**: Reverse proxy for secure access.

### Requirements
- [Docker](https://docs.docker.com/engine/install/)
- [Docker Compose](https://docs.docker.com/compose/install/)

### How to run
1. **Setup `.env` file (Configure env variables)**
```
cp .env.example .env
```
2. **Optional:** Generate self-signed certificates
```
./scripts/generate-certs.sh 
``` 
3. **Deploy Docker Compose**
```
# Use profiles to select http or https
# Deploy on http
docker compose --profile http up --build -d

# Deploy on https
docker compose --profile https up --build -d
```

### Avaliability
#### NextCloud
NextCloud instance will be avaliable on `localhost/cloud`(use credentials from `.env` file)

