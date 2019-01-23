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
    - Tip: You can setup a [.pgpass](https://www.postgresql.org/docs/current/static/libpq-pgpass.html) password file to automate login (i.e., that you do not need to retype the password).
* Change password: https://www.postgresql.org/docs/current/static/sql-alterrole.html
    - [psql] `ALTER ROLE app_user WITH PASSWORD 'new_password';`
* Create database: https://www.postgresql.org/docs/current/static/sql-createdatabase.html
    - [psql] `CREATE DATABASE app_database WITH OWNER app_user ENCODING 'UTF8';`
* Drop database: https://www.postgresql.org/docs/current/static/sql-dropdatabase.html
    - [psql] `DROP DATABASE app_database;`

## Import / Run SQL Code

Two options to execute SQL code:

* [shell] psql −U app_user −f /full/path/to/create_schema.sql app_database
* [psql] `\i /full/path/to/create_schema.sql`

Steps to import the [MONDIAL database](https://www.dbis.informatik.uni-goettingen.de/Mondial/) dump:

1. Create a [user](https://www.postgresql.org/docs/current/sql-createuser.html)/[role](https://www.postgresql.org/docs/current/sql-createrole.html) called `mondial` with password `mondial` and a [database](https://www.postgresql.org/docs/current/sql-createdatabase.html) called `mondial_db` owned by the mondial user

    ```none
    # [bash]
    psql -U postgres postgres
    # [psql]
    CREATE USER mondial WITH PASSWORD 'mondial';
    CREATE DATABASE mondial_db WITH OWNER mondial;
    # Quit interactive session
    \q
    ```

2. Download the schema (`create_schema.sql`) and input values (`insert_inputs.sql`) from [Canvas](https://chalmers.instructure.com/courses/3790/files/folder/assignments)
3. Import the schema and values

    ```bash
    psql −q −U mondial −f ./create_schema.sql mondial_db
    psql −q −U mondial −f ./insert_inputs.sql mondial_db
    ```

4. Connect to the mondial database with the terminal client psql

    ```bash
    psql −U mondial mondial_db
    ```

5. Verify whether the following query yields `1318`

    ```none
    SELECT COUNT(iatacode) FROM airport;
    ```

Tip: You can use [dropdb](https://www.postgresql.org/docs/current/app-dropdb.html) or [sql-dropdatabase](https://www.postgresql.org/docs/current/sql-dropdatabase.html) `DROP DATABASE mondial;` to destroy your database and start from scratch.
