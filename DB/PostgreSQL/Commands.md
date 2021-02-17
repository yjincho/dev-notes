# PostgreSQL

## Listing Databases

```
postgres=# \l
```

## Listing Tables

```
postgres=# \dt
```

## Listing Roles

```
postgres=# \du
```

## Switching Databases

```
postgres=# \c <dbname>
You are now connected to database "<dbname>" as user "postgres".
dbname=# 
```

## Exiting from psql

```
postgres=# \q
```

## Creating a Table

```
postgres=# CREATE TABLE playground (
    equip_id serial PRIMARY KEY,
    type varchar (50) NOT NULL,
    color varchar (25) NOT NULL,
    location varchar(25) check (location in ('north', 'south', 'west', 'east', 'northeast', 'southeast', 'southwest', 'northwest')),
    install_date date
);
```

## Deleting a Table

```
postgres=# DROP TABLE playground;
```

## Deleting All Tables

```
postgres=# DROP SCHEMA public CASCADE;
postgres=# CREATE SCHEMA public;

postgres=# GRANT ALL ON SCHEMA public TO postgres;
postgres=# GRANT ALL ON SCHEMA public TO public;
```

## Adding, Querying, and Deleting Data in a Table

```
postgres=# INSERT INTO playground (type, color, location, install_date) VALUES ('slide', 'blue', 'south', '2017-04-28');
```

```
postgres=# SELECT * FROM playground;
```

```
postgres=# DELETE FROM playground WHERE type = 'slide';
```

## Adding and Deleting Columns from a Table

```
postgres=# ALTER TABLE playground ADD last_maint date;
```

```
postgres=# ALTER TABLE playground DROP last_maint;
```

## Updating Data in a Table

```
postgres=# UPDATE playground SET color = 'red' WHERE type = 'swing';
```

# Reference

- [PostgreSQL Tutorial](https://www.postgresqltutorial.com/)
