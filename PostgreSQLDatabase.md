# PostgreSQL Database Initialization

## Table of Contents

- [Installations](#Installations)
- [Connection](#Connection)
- [Database-Initialization](#Database-Initialization)
- [Schema](#Schema)
- [Optional](#Optional)

## A new Database

Installation:

PostgreSQL

```bash
sudo apt install postgresql postgresql-contrib
```

DBeaver

```bash
Sudo snap install dbeaver-ce
```

## Connection

Create a connection with PostgreSQL over DBeaver:

```bash
Database menu> New Database Connection> PostgreSQL
```

## Database-Initialization

Switch to user

```bash
sudo -i -u postgres
```

Connection Establishment to PostgreSQL

```bash
psql
```

Create a superuser `admin` with a Password `admin`

```postgresql
postgres=# CREATE ROLE admin WITH LOGIN SUPERUSER CREATEDB CREATEROLE PASSWORD 'admin';
```

Create `developer` user with a Password `developer`

```postgresql
postgres=# CREATE USER developer WITH ENCRYPTED PASSWORD 'developer';
```

A new Database `coursedb`

```postgresql
postgres=# CREATE DATABASE coursedb;
```

Privileges to a user for the Database

```postgresql
postgres=# GRANT ALL PRIVILEGES ON DATABASE coursedb TO developer;
```

Connection establishment with database `coursedb`

```postgresql
postgres=# \c coursedb;
```

Connection establishment with user

```postgresql
coursedb=# \c coursedb developer;
```

## Create a new Schema

New Schema

```postgresql
coursedb=# \c CREATE SCHEMA testschema
```

## Optional

List of Database >>  `\l`

List of User >>  `\du`

List of Schema >>  `\dn`
