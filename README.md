
# Getring Started on a CodeCatalyst Dev Environment

This is a quick overview...

### Create a Database

First, connect to PostgreSQL 

```
psql --host=localhost --username=postgres
```

Then, create a new database called mydatabase

```
create database mydatabase;
```

Quit PostgreSQL

```
\q
````

### Run Liquibase

Now run liquibase to create the schema

```
liquibase update
```

### Confirm the change

First, connect to the new PostgreSQL database

```
psql --host=localhost --username=postgres --dbname=mydatabase
```

Query the new table 

```
select * from actor;
```

Quit PostgreSQL

```
\q
````

### Rollback 

If you look in the changlogs folder, you will see two changelogs are applied. The first creates the actor table and the second adds an additional column. Let's roll back the last command. 

```
liquibase rollbackCount 1
```

### Confirm the Rollback

First, connect to the new PostgreSQL database

```
psql --host=localhost --username=postgres --dbname=mydatabase
```

Query the new table 

```
select * from actor;
```

Quit PostgreSQL

```
\q