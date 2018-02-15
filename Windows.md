# Windows

## Preparation

1. Familiarize yourself with the very basics of the Windows command line<sup>[1](#cmd)</sup> (5'): https://www.makeuseof.com/tag/a-beginners-guide-to-the-windows-command-line/
2. Install the [Chocolatey](https://chocolatey.org/) package manager: https://youtu.be/hfgZYpo5moA?t=1m2s
    1. Run your `cmd` shell *Run as administrator* !
    2. [Install command](https://chocolatey.org/install) `@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"`
    3. Verify the installation via `choco --version` and it should output the installed version (e.g., `0.10.8`)


<sup><a name="cmd">1.</a> You might want to use a better console emulator at some point (e.g., [cmder](http://cmder.net/) or [Hyper](https://hyper.is/)).</sup>

## PostgreSQL

1. Install [PostgreSQL](https://www.postgresql.org/) with Chocolatey `choco install postgresql -y` (as admin!)
2. Reopen your shell (not as admin)
3. Run `SET PGCLIENTENCODING=UTF8` in your command line
4. Start [psql](https://www.postgresql.org/docs/current/static/app-psql.html) shell: `psql -U postgres postgres` (`psql -U username dbname`) using the default password `Postgres1234`
5. Check for any startup warnings. If you see a warning that the console code page differs from Windows code page:

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

1. Install [Maven](https://maven.apache.org/index.html) with Chocolatey `choco install maven -y` (as admin! This will also install a JDK 8 if not present)
2. Reopen your shell (not as admin)
3. Verify installation with `mvn --version`

    ```
    C:\Users\joe>mvn --version
    Apache Maven 3.5.2 (138edd61fd100ec658bfa2d307c43b76940a5d7d; 2017-10-18T09:58:13+02:00)
    Maven home: C:\ProgramData\chocolatey\lib\maven\apache-maven-3.5.2\bin\..
    Java version: 1.8.0_162, vendor: Oracle Corporation
    Java home: C:\Program Files\Java\jdk1.8.0_162\jre
    Default locale: en_US, platform encoding: Cp1252
    OS name: "windows 10", version: "10.0", arch: "amd64", family: "windows"
    ```

## MongoDB

1. Install [MongoDB](https://www.mongodb.com/) with Chocolatey `choco install mongodb -y` (as admin!)
2. Reopen your shell (not as admin)
3. Start the [mongo](https://docs.mongodb.com/manual/mongo/) shell: `mongo`
4. Check whether `show dbs` lists all your current databases
