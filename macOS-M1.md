# macOS - M1 Silicon

## Preparation

1. Familiarize yourself with the very basics of the [macOS command line](http://blog.teamtreehouse.com/introduction-to-the-mac-os-x-command-line) (5')
2. Install the [Homebrew](https://brew.sh) package manager ([video](https://www.youtube.com/watch?v=Yr5gyqeMadk))
    1. Install: `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
    2. Check installation: `brew doctor`
    3. Update: `brew update`

## PostgreSQL

1. Install [PostgreSQL](https://www.postgresql.org/) with Homebrew: [Video](https://www.youtube.com/watch?v=IbVPbF7HTL4&t=9s)
      * Install: `brew install postgresql`
      * NOTE: This will automatically create a superuser (i.e., admin) called `postgres` with no password
2. Start the postgres server: `pg_ctl -D /opt/homebrew/var/postgres start`
3. Start the [psql](https://www.postgresql.org/docs/current/static/app-psql.html) shell client: `psql postgres postgres` (`psql dbname username` note the `-U` option comes before the dbname unlike in the video!)
4. Check whether `\l` lists all your current databases

Tip: You can setup the postgres server as a service (i.e., auto-start with your computer) using `brew services start postgresql`

## MongoDB

1. Install [MongoDB](https://www.mongodb.com/) with Homebrew ([docs](https://github.com/mongodb/homebrew-brew))
    1. Run `brew tap mongodb/brew`
    2. Install: `brew install mongodb-community@4.4`
    3. Run daemon: `mongod --config /opt/homebrew/etc/mongod.conf`
2. Start the [mongo](https://docs.mongodb.com/manual/mongo/) shell: `mongo`
3. Check whether `show dbs` lists all your current databases

*Note: If 4.4 refuses to work, opt for the latest by using `mongodb-community`.*