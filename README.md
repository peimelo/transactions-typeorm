# Go Barber

After clone this repository, install the dependencies:

```
yarn
```

Deixe o Docker executando e rode o comando para criar o database `gostack_desafio06`:

```
docker-compose up -d
```

---

Rode as migrations:

```
yarn typeorm migration:run
```

Se ocorrer o erro:

```
Error during migration run:
QueryFailedError: function uuid_generate_v4() does not exist
```

entre dentro na linha de comando do psql do Docker para criar a extensão necessária (senha `docker`):

```
docker exec -it transactions-typeorm_database_1 psql -U postgres -W gostack_desafio06

gostack_desafio06=# CREATE EXTENSION IF NOT EXISTS "uuid-ossp";

```

daí rode as migrations novamente.

---

To run the project:

```
yarn dev:server
```

Open your browser in `http://localhost:3333`
