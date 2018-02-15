# macOS

## Preparation

1. Familiarize yourself with the very basics of the macOS command line (5'): http://blog.teamtreehouse.com/introduction-to-the-mac-os-x-command-line
2. Install the [Homebrew](https://brew.sh) package manager: https://www.youtube.com/watch?v=Yr5gyqeMadk
    * Install: `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
    * Check installation: `brew doctor`
    * Update: `brew update`

## PostgreSQL

1. Install [PostgreSQL](https://www.postgresql.org/) with Homebrew: https://www.youtube.com/watch?v=IbVPbF7HTL4&t=9s
      * Install: `brew install postgresql`
      * Run daemon: `pg_ctl -D /usr/local/var/postgres start`
2. Start the [psql](https://www.postgresql.org/docs/current/static/app-psql.html) shell: `psql -U postgres postgres` (`psql -U username dbname` note the `-U` option comes before the dbname unlike in the video!)
3. Check whether `\l` lists all your current databases

## MongoDB

1. Install [MongoDB](https://www.mongodb.com/) with Homebrew: https://www.youtube.com/watch?v=yPBgsyY8Rmk&t=9s
    * Textual (plus tip on how to setup as a background service): https://gist.github.com/nrollr/9f523ae17ecdbb50311980503409aeb3
    * Install: `brew install mongodb`
    * Run daemon: `mongod --config /usr/local/etc/mongod.conf`
2. Start the [mongo](https://docs.mongodb.com/manual/mongo/) shell: `mongo`
3. Check whether `show dbs` lists all your current databases
