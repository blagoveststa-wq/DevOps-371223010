# 0003. Where the service runs / Къде работи услугата

**Status / Статус:** Accepted

## Context / Контекст

The service must run somewhere reachable by users, not only on a laptop. / Услугата трябва да работи на място, достъпно за потребителите, а не само на лаптоп.

## Options / Варианти

| Option | Pros | Cons |
|---|---|---|
| One virtual server with Docker Compose | Simple, cheap, full control, teaches Linux and deployment basics | Manual updates; single point of failure |
| Managed platform (PaaS) | Little operations work | Hides what we want to learn; vendor lock-in |
| Kubernetes | Scaling, self-healing | Too complex for a small app and a short course |

## Decision / Решение

We run the service on **one virtual server with Docker Compose** (`infra/servers`). / Пускаме услугата на **един виртуален сървър с Docker Compose** (`infra/servers`).

## Consequences / Последствия

- We must manage the server ourselves: updates, access, backups. / Сами поддържаме сървъра: обновления, достъп, резервни копия.
- Deployment is repeatable through Compose files kept in the repo. / Внедряването е повторяемо чрез Compose файлове в хранилището.
- We can move to a platform later with a new ADR. / По-късно можем да преминем към платформа с ново решение.