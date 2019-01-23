# macOS

## Preparation

1. Familiarize yourself with the very basics of the macOS command line (5'): http://blog.teamtreehouse.com/introduction-to-the-mac-os-x-command-line
2. Install the [Homebrew](https://brew.sh) package manager: https://www.youtube.com/watch?v=Yr5gyqeMadk
    * Install: `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
    * Check installation: `brew doctor`
    * Update: `brew update`

## PostgreSQL

1. Install [PostgreSQL](https://www.postgresql.org/) with Homebrew: [Video](https://www.youtube.com/watch?v=IbVPbF7HTL4&t=9s)
      * Install: `brew install postgresql`
2. Start the postgres server: `pg_ctl -D /usr/local/var/postgres start`
3. Start the [psql](https://www.postgresql.org/docs/current/static/app-psql.html) shell client: `psql -U postgres postgres` (`psql -U username dbname` note the `-U` option comes before the dbname unlike in the video!)
4. Check whether `\l` lists all your current databases

Tip: You can setup the postgres server as a service (i.e., auto-start with your computer) using `brew services start postgresql`

## Java Development Kit (JDK)

1. Download and install a Java JDK: https://www.oracle.com/technetwork/java/javase/downloads/jdk11-downloads-5066655.html

    > Checkout [this StackOverflow post](https://stackoverflow.com/a/52524114/6875981) for more (advanced) installation options

2. Verify installation with `java --version`:

    ```none
    openjdk 11.0.1 2018-10-16
    OpenJDK Runtime Environment 18.9 (build 11.0.1+13)
    OpenJDK 64-Bit Server VM 18.9 (build 11.0.1+13, mixed mode)
    ```

## Maven (for jdbc project in Assignment 2)

1. Install [Maven](https://maven.apache.org/index.html) with Homebrew: [Tutorial](https://github.com/rajivkanaujia/alphaworks/wiki/Installing-Maven)
    * `brew install maven`
2. Verify installation with `mvn --version`:

    ```none
    Apache Maven 3.6.0 (97c98ec64a1fdfee7767ce5ffb20918da4f719f3; 2018-10-24T20:41:47+02:00)
    Maven home: /usr/local/Cellar/maven/3.6.0/libexec
    Java version: 11.0.1, vendor: Oracle Corporation, runtime: /Library/Java/JavaVirtualMachines/openjdk-11.0.1.jdk/Contents/Home
    Default locale: en_CH, platform encoding: UTF-8
    OS name: "mac os x", version: "10.13.6", arch: "x86_64", family: "mac"
    ```

## MongoDB

1. Install [MongoDB](https://www.mongodb.com/) with Homebrew: https://www.youtube.com/watch?v=yPBgsyY8Rmk&t=9s
    * Textual (plus tip on how to setup as a background service): https://gist.github.com/nrollr/9f523ae17ecdbb50311980503409aeb3
    * Install: `brew install mongodb`
    * Run daemon: `mongod --config /usr/local/etc/mongod.conf`
2. Start the [mongo](https://docs.mongodb.com/manual/mongo/) shell: `mongo`
3. Check whether `show dbs` lists all your current databases
