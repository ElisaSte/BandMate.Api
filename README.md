# BandMate.Api
ASP.NET Core backend for the BandMate app

## Local database

The app uses PostgreSQL with the PostGIS extension, run locally via Docker Compose.

Requirements: [Docker Desktop](https://www.docker.com/products/docker-desktop/) (WSL 2 backend on Windows).

```bash
cp .env.example .env      # PowerShell: Copy-Item .env.example .env
docker compose up -d      # start PostgreSQL + PostGIS
docker compose ps         # wait until STATUS shows "(healthy)"
```

Connection: `localhost:5432` (or `POSTGRES_PORT`), with the credentials from `.env`.

Useful commands:

| Command | Effect |
| --- | --- |
| `docker compose down` | Stop the database (data is kept in the `pgdata` volume) |
| `docker compose down -v` | Stop and **delete all data** |
| `docker compose exec db psql -U bandmate -d bandmate` | Open a `psql` shell |
