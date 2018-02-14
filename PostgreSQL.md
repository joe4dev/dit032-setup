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
* Create database: https://www.postgresql.org/docs/current/static/sql-createdatabase.html
    - [psql] `CREATE DATABASE app_database;`
* Drop database: https://www.postgresql.org/docs/current/static/sql-dropdatabase.html
    - [psql] `DROP DATABASE app_database;`

## Import / Run SQL Code

* [shell] psql −U app_user −f ./create_schema.sql app_database
* [psql] `\i /your/full/path/goes/here/create_schema.sql`
