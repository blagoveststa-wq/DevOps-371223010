# 0002. Database for Lab 4 

**Status:** Accepted

## Context 

Notes are currently kept in memory and lost on restart. In Lab 4 they must be persisted.

## Options 

| Option | Pros | Cons |
|---|---|---|
| SQLite | No extra server, trivial setup | A file inside the container: lost with it; poor fit for several instances |
| PostgreSQL | Separate service, real-world standard, works with `DATABASE_URL`, supports `/ready` check | One more container to run and secure |
| MongoDB | Flexible schema | Our notes are simple and structured; the app is built for SQL |

## Decision 

We use **PostgreSQL**, configured through `DATABASE_URL`. / Използваме **PostgreSQL**, настроен чрез `DATABASE_URL`.

## Consequences 

- A database container must run next to the app (Lab 4). / Нужен е контейнер с база до приложението.
- `/ready` returns 503 while the database is unreachable. / `/ready` връща 503, докато базата не се достига.
- Credentials must not be committed; they are passed as environment variables. / Паролите не се комитват, а се подават като променливи на средата.