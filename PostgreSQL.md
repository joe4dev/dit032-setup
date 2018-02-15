# PostgreSQL

* Docs: https://www.postgresql.org/docs/10/static/index.html
* Curated list of resources: https://github.com/dhamaniasad/awesome-postgres

## GUI Apps

* pgAdmin 4: https://www.pgadmin.org/download/

## psql shell

Start the psql shell with `psql postgres` (`psql -U username dbname`)`

* Docs: https://www.postgresql.org/docs/current/static/app-psql.html
* Cheat Sheet: https://gist.github.com/Kartones/dd3ff5ec5ea238d4c546
* Show help `\?`
* List databases `\l`
* List users `\du`
* Quit interactive session `\q` or `CTRL+D`

## Administration

* Create user: https://www.postgresql.org/docs/current/static/sql-createrole.html
    - [psql] `CREATE ROLE app_user WITH LOGIN PASSWORD 'app_password';`
    - Tip: You can setup a [.pgpass](https://www.postgresql.org/docs/current/static/libpq-pgpass.html) password file if you don't want to automate login.
* Change password: https://www.postgresql.org/docs/current/static/sql-alterrole.html
    - [psql] `ALTER ROLE app_user WITH PASSWORD 'new_password';`
* Create database: https://www.postgresql.org/docs/current/static/sql-createdatabase.html
    - [psql] `CREATE DATABASE app_database WITH OWNER app_user ENCODING 'UTF8';`
* Drop database: https://www.postgresql.org/docs/current/static/sql-dropdatabase.html
    - [psql] `DROP DATABASE app_database;`

## Import / Run SQL Code

* [shell] psql −U app_user −f /full/path/to/create_schema.sql app_database
* [psql] `\i /full/path/to/create_schema.sql`
