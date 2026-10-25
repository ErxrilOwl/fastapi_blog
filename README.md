### Postgresql Sample with Docker
```sh
docker run -d --name postgres-blog -p 5432:5432 -e POSTGRES_PASSWORD=secret -v pgdata18:/var/lib/postgresql postgres:latest
```

```sh
docker exec -it postgres-blog psql -U postgres -c "CREATE USER bloguser WITH PASSWORD 'blogpass';"
docker exec -it postgres-blog psql -U postgres -c "CREATE DATABASE blog OWNER bloguser;"
docker exec -it postgres-blog psql -U bloguser -d blog
```


### Common Alembic Command
```sh
uv run alembic init -t async alembic
uv run alembic revision --autogenerate -m "initial schema"
uv run alembic upgrade head
uv run alembic downgrade -1
```


### Testing
```sh
uv run pytest tests/test_demo.py -v
```