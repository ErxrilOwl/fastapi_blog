### Postgresql Sample with Docker
```sh
docker run -d --name postgres-blog -p 5432:5432 -e POSTGRES_PASSWORD=secret -v pgdata18:/var/lib/postgresql postgres:latest
```

```sh
docker exec -it postgres-blog psql -U postgres -c "CREATE USER bloguser WITH PASSWORD 'blogpass';"
docker exec -it postgres-blog psql -U postgres -c "CREATE DATABASE blog OWNER bloguser;"
```