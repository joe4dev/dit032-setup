# Windows

## Preparation

1. Familiarize yourself with the very basics of the Windows command line<sup>[1](#cmd)</sup> (5'): https://www.makeuseof.com/tag/a-beginners-guide-to-the-windows-command-line/
2. Don't forget to re-open your shell whenever you update any system environment variables.
3. Keep in mind to change the `/` in file paths to `\` accordingly

<sup><a name="cmd">1.</a> You might want to use a better console emulator at some point (e.g., [cmder](http://cmder.net/) or [Hyper](https://hyper.is/)).</sup>

## PostgreSQL

1. Install [PostgreSQL](https://www.postgresql.org/): https://www.youtube.com/watch?v=e1MwsT5FJRQ
    * Download: https://www.enterprisedb.comcho/downloads/postgres-postgresql-downloads
    * Textual tutorial: http://www.postgresqltutorial.com/install-postgresql/
2. Run `SET PGCLIENTENCODING=UTF8` in your command line
3. Start [psql](https://www.postgresql.org/docs/current/static/app-psql.html) shell: `psql -U postgres postgres` (`psql -U username dbname`)
4. Check for any startup warnings. If you see a warning that the console code page differs from Windows code page:

    ```none
    psql (10.2)
    WARNING: Console code page (437) differs from Windows code page (1252)
         8-bit characters might not work correctly. See psql reference
         page "Notes for Windows users" for details.
    Type "help" for help.

    postgres=#
    ```
   1. Change the [active console code page](https://ss64.com/nt/chcp.html) respectively using `chcp 1252` (or 65001 for UTF-8)

5. Check whether `\l` lists all your current databases

## Java SDK (for jdbc project)

1. Install the Java SDK: https://www.youtube.com/watch?v=fTpDHQ_V0Fw
    1. Download: http://www.oracle.com/technetwork/java/javase/downloads/jdk9-downloads-3848520.html
    2. Run the installer
    3. Setup system variable `JAVA_HOME` pointing to your *JDK* (e.g., `C:\Program Files\Java\jdk-9.0.4`)
    4. Add `%JAVA_HOME%\bin` to your Path (don't forget to click OK, OK)
2. Check whether `javac --version` displays the version (e.g., `javac 9.0.4`)

## Maven (for jdbc project)

1. Install [Maven](https://maven.apache.org/index.html): [Video](https://youtu.be/dlPjiYyVSlc?t=21s) or [Tutorial](https://downlinko.com/download-install-apache-maven-3-5-0-windows.html)
    1. Download binary zip: https://maven.apache.org/download.cgi
    2. Unzip into a folder (e.g., `C:\dev\Maven`)
    3. Setup system variables `M2_HOME` and `MAVEN_HOME` pointing to your folder (e.g., `C:\dev\Maven`) wherein bin, boot, conf, lib etc reside
    4. Add `%M2_HOME%\bin` to your Path (don't forget to click OK, OK)
2. Check whether `mvn --version` displays the version. Example:

    ```none
    C:\Users\joe>mvn --version
    Apache Maven 3.5.2 (138edd61fd100ec658bfa2d307c43b76940a5d7d; 2017-10-18T09:58:13+02:00)
    Maven home: C:\dev\Maven\bin\..
    Java version: 9.0.4, vendor: Oracle Corporation
    Java home: C:\Program Files\Java\jdk-9.0.4
    Default locale: en_US, platform encoding: Cp1252
    OS name: "windows 10", version: "10.0", arch: "amd64", family: "windows"
    ```

## MongoDB

1. Install [MongoDB](https://www.mongodb.com/): [short (4')](https://www.youtube.com/watch?v=_RQ4lET5ejw) or [long (12')](https://www.coursera.org/learn/introduction-mongodb/lecture/Hadhu/installing-mongodb-on-windows) tutorial
    1. Download the *Community Server*: https://www.mongodb.com/download-center?jmp=nav#community
    2. Run the installer (choose *Complete*, you can uncheck the Compass GUI if you wanna speed up installation)
    3. Setup system variable `MONGO_HOME` pointing to your installation (e.g., `C:\Program Files\MongoDB\Server\3.6`)
    4. Add `%MONGO_HOME%\bin` to your Path (don't forget to click OK, OK)
2. Create a data directory: `mkdir -p C:\data\db`
3. Run the daemon `mongod` and keep this shell open (it should finally show `NETWORK  [initandlisten] waiting for connections on port 27017`)
4. Start the [mongo](https://docs.mongodb.com/manual/mongo/) shell in a new shell: `mongo`
5. Check whether `show dbs` lists all your current databases (should list admin and local)
