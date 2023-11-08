# Развёртывание проекта

### Поднять Postgres
```shell
docker run --name deal-db -p 5434:5432 -e POSTGRES_USER=deal -e POSTGRES_PASSWORD=deal postgres:14
```

### Создать схему deal
```sql
create schema deal;
create role deal;
alter schema deal owner to deal;
```

### Установить схему по умолчанию deal
```sql
set search_path to deal;
```

### Создать кастомные типы данных для Java Enum 
```sql
create type credit_status_enum as enum ('CALCULATED', 'ISSUED');
```