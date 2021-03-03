# Windows

> Keep an eye on version numbers and remember to update them if you use another version!

## Preparation

1. Familiarize yourself with the very basics of the Windows command line<sup>[1](#cmd)</sup> (5'): https://www.makeuseof.com/tag/a-beginners-guide-to-the-windows-command-line/
2. Don't forget to re-open your shell whenever you update any system environment variables.
3. Keep in mind to change the `/` in file paths to `\` accordingly

<sup><a name="cmd">1.</a> You might want to use a better console emulator at some point (e.g., [cmder](http://cmder.net/) or [Hyper](https://hyper.is/)).</sup>

## PostgreSQL

1. Install [PostgreSQL](https://www.postgresql.org/download/windows/): [Tutorial](http://www.postgresqltutorial.com/install-postgresql/) or [Video](https://www.youtube.com/watch?v=e1MwsT5FJRQ)
    * Download: https://www.enterprisedb.com/downloads/postgres-postgresql-downloads
2. Add `C:\Program Files\PostgreSQL\13\bin;` to the PATH (computer => properties => advanced system settings=> Environment Variables => System Variables) as described [here](https://stackoverflow.com/questions/30401460/postgres-psql-not-recognized-as-an-internal-or-external-command?answertab=active#tab-top)
3. Run `setx PGCLIENTENCODING UTF8` in your command line
4. Start [psql](https://www.postgresql.org/docs/current/static/app-psql.html) shell: `psql postgres postgres` (`psql dbname username`)
5. Check for any startup warnings. If you see a warning that the console code page differs from Windows code page:

    ```none
    psql (10.2)
    WARNING: Console code page (437) differs from Windows code page (1252)
         8-bit characters might not work correctly. See psql reference
         page "Notes for Windows users" for details.
    Type "help" for help.

    postgres=#
    ```
   1. Change the [active console code page](https://ss64.com/nt/chcp.html) respectively using `chcp 1252` (or 65001 for UTF-8)

6. Check whether `\l` lists all your current databases

### Start the server

How do I start the PostgreSQL server (e.g., after re-booting)?

```shell
set PGDATA=C:\Program Files\PostgreSQL\13\data
pg_ctl start
```

### Create postgres superuser

How can I create a postgres superuser if none exists?

* [psql] `CREATE USER postgres WITH SUPERUSER PASSWORD 'postgres'`

## MongoDB

### Server
1. Install [MongoDB](https://www.mongodb.com/): [short (4')](https://www.youtube.com/watch?v=_RQ4lET5ejw) or [long (12')](https://www.coursera.org/learn/introduction-mongodb/lecture/Hadhu/installing-mongodb-on-windows) tutorial
    1. Download the *Community Server*: https://www.mongodb.com/download-center/community
    2. Run the installer (choose *Complete*, you can uncheck the Compass GUI if you wanna speed up installation)
    3. Setup system variable `MONGO_HOME` pointing to your installation (e.g., `C:\Program Files\MongoDB\Server\4.4`)
    4. Add `%MONGO_HOME%\bin` to your Path (don't forget to click OK, OK)
2. Create a data directory: `mkdir -p C:\data\db`
3. Run the daemon `mongod` and keep this shell open (it should finally show `NETWORK  [initandlisten] waiting for connections on port 27017`)
4. Start the [mongo](https://docs.mongodb.com/manual/mongo/) shell in a new shell: `mongo`
5. Check whether `show dbs` lists all your current databases (should list admin and local)

### Tools
1. Download and run the "Database Tools" installer: https://www.mongodb.com/try/download/database-tools
2. Add the installed binary directory to your Path (e.g. by default this would be `C:\Program Files\MongoDB\Tools\100\bin`)
3. Open a new command prompt and call `mongoimport --version`, if it returns no errors installation was succesful

Detailed steps on how to add a directory to your PATH can be found [here](https://docs.mongodb.com/database-tools/installation/installation-windows/#make-the-db-tools-available-in-your-path).