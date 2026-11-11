# did-method-plc Notes

[plc.directory](https://plc.directory) is a key part of DID-PLC.

DID-PLC is a popular DID method used on the ATProto ATmosphere — which includes Bluesky, Blacksky, Leaflet, and others.

The source-code for [plc.directory](https://plc.directory) open-source, and available here:

* https://github.com/did-method-plc/did-method-plc

## Running plc.directory Locally

If you are a computer-programmer working with ATProto, then you may want to run your own local alternative to [plc.directory](https://plc.directory)

Here are the steps to do that.

### Step 1: clone the git repository

```
git clone https://github.com/did-method-plc/did-method-plc.git
```

### Step 2: go inside

```
cd did-method-plc
```

-----

Now you have to decide whether you want to run it bare on your computer, or run it within a Docker container.

-----

### Bare

In this section are the instructions if you want to run the `did-method-plc` on your bare computer (rather than inside of a Docker container).

#### (Bare) Step 3: install dependencies

```
pnpm install --pm-on-fail=ignore
```

#### (Bare) Step 4: build

```
pnpm --pm-on-fail=ignore build
```

#### (Bare) Step 5: run server

```
DATABASE_URL=postgres://postgres@localhost:5433/plc \
PORT=2582 \
DEBUG_MODE=1 \
ENABLE_MIGRATIONS=true \
pnpm --pm-on-fail=ignore start
```
Where you would replace `postgres://postgres@localhost:5433/plc` with whatever the URL to your Postgres sever is.

And, you would replace `2582` with whatever you want your port to be.

---

### Docker

In this section are the instructions if you want to run the `did-method-plc` inside of a Docker container (rather than on your bare computer).

#### (Docker) Step 3: directory

```
cd did-method-plc/packages/server
```

#### (Docker) Step 4: docker

```
docker compose -f pg/docker-compose.yaml up -d db
```

#### (Docker) Step 5: run server

```
DATABASE_URL=postgresql://pg:password@localhost:5432/postgres \
PORT=2582 \
DEBUG_MODE=1 \
ENABLE_MIGRATIONS=true \
pnpm --pm-on-fail=ignore start
```

-----

## Postgres

To look at the Postgres database inside the Docker container you can do something such as the following:

```
docker exec -it pg-db-1 psql -U pg -d postgres
```

Some useful commands:

```
\l              list databases
\dt             list tables
\d table_name   describe a table
SELECT * FROM table_name LIMIT 10;
\q              quit
```
