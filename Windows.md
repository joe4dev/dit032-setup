# Windows

## Preparation

1. Familiarize yourself with the very basics of the Windows command line (5'): https://www.makeuseof.com/tag/a-beginners-guide-to-the-windows-command-line/

## PostgreSQL

1. Install [PostgreSQL](https://www.postgresql.org/): https://www.youtube.com/watch?v=e1MwsT5FJRQ
    * Download: https://www.enterprisedb.com/downloads/postgres-postgresql-downloads
    * Textual tutorial: http://www.postgresqltutorial.com/install-postgresql/
2. Run `SET PGCLIENTENCODING=UTF8` in your command line
3. Start [psql](https://www.postgresql.org/docs/current/static/app-psql.html) shell: `psql -U postgres postgres` (`psql -U username dbname`)
4. Check for any startup warnings. If you see a warning that the console code page differs from Windows code page:

    ```
    psql (10.2)
    WARNING: Console code page (437) differs from Windows code page (1252)
         8-bit characters might not work correctly. See psql reference
         page "Notes for Windows users" for details.
    Type "help" for help.

    postgres=#
    ```
   1. Change the [active console code page](https://ss64.com/nt/chcp.html) respectively using `chcp 1252` (or 65001 for UTF-8)

5. Check whether `\l` lists all your current databases

## MongoDB

1. Install [MongoDB](https://www.mongodb.com/)
    * Short tutorial (4'): https://www.youtube.com/watch?v=_RQ4lET5ejw
    * Long tutorial (12'): [Installing MongoDB on Windows](https://www.coursera.org/learn/introduction-mongodb/lecture/Hadhu/installing-mongodb-on-windows)
    * Run the daemon: `mongod --port 27017 --dbpath C:\MongoDB\data\db`
2. Start the [mongo](https://docs.mongodb.com/manual/mongo/) shell: `mongo`
3. Check whether `show dbs` lists all your current databases
