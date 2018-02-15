# Windows

## Preparation

1. Familiarize yourself with the very basics of the Windows command line<sup>[1](#cmd)</sup> (5'): https://www.makeuseof.com/tag/a-beginners-guide-to-the-windows-command-line/
2. Install the [Chocolatey](https://chocolatey.org/) package manager: https://youtu.be/hfgZYpo5moA?t=1m2s
    1. Run your `cmd` shell *Run as administrator* !
    2. [Install command](https://chocolatey.org/install) `@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"`
    3. Verify the installation via `choco --version` and it should output the installed version (e.g., `0.10.8`)


<sup><a name="cmd">1.</a> You might want to use a better console emulator at some point (e.g., [cmder](http://cmder.net/) or [Hyper](https://hyper.is/)).</sup>

## PostgreSQL

1. Install [PostgreSQL](https://www.postgresql.org/): https://www.youtube.com/watch?v=e1MwsT5FJRQ
    * Download: https://www.enterprisedb.comcho/downloads/postgres-postgresql-downloads
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

## Maven (for jdbc project)

1. Install [Maven](https://maven.apache.org/index.html): https://youtu.be/dlPjiYyVSlc?t=21s
    1. Download binary zip: https://maven.apache.org/download.cgi
    2. Unzip into a folder (e.g., `C:\dev\Maven`)
    3. Setup system variables `M2_HOME` and `MAVEN_HOME` pointing to your folder (e.g., `C:\dev\Maven`)
    4. Add ``%M2_HOME%\bin`` and `%MAVEN_HOME%\bin` to your PATH
2. Verify installation with `mvn --version`

## MongoDB

1. Install [MongoDB](https://www.mongodb.com/)
    * Short tutorial (4'): https://www.youtube.com/watch?v=_RQ4lET5ejw
    * Long tutorial (12'): [Installing MongoDB on Windows](https://www.coursera.org/learn/introduction-mongodb/lecture/Hadhu/installing-mongodb-on-windows)
    * Run the daemon: `mongod --port 27017 --dbpath C:\MongoDB\data\db`
2. Start the [mongo](https://docs.mongodb.com/manual/mongo/) shell: `mongo`
3. Check whether `show dbs` lists all your current databases
