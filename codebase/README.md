# Webby Monorepo

This repository contains:

- `apps/cms` (Payload CMS)
- `apps/frontend` (Next.js site)

## Run Everything with Docker

From the repository root:

```bash
docker compose up --build
```

Services:

- Frontend: http://localhost:3000
- CMS: http://localhost:3001
- PostgreSQL: localhost:5432
- SonarQube: http://localhost:9000

## SonarQube for CMS and Frontend

Start SonarQube services:

```bash
docker compose up -d sonardb sonarqube
```

Run CMS scan:

```bash
docker compose --profile sonar-scan run --rm scanner-cms
```

Run frontend scan:

```bash
docker compose --profile sonar-scan run --rm scanner-frontend
```

`SONAR_TOKEN` is read from `.env`.
