# Linux

You probably know what you need to do anyways, but here is a compacted guide to not waste your time :)

## PostgreSQL
### Installation
**Ubuntu**
```
sudo apt install postgresql postgresql-contrib
```
**Arch**
```
sudo pacman -S postgresql
```
**Fedora**
```
sudo dnf install postgresql
```
### Setup
Once installed make check if the postgresql server is running (or at least exists) with:
```
systemctl status postgresql
```
If it is not active use the following command to have it automatically start:
```
sudo systemctl enable --now postgresql
```
If it fails, don't worry we need to some configuration first.  
Login and start a shell with the following command:
```
sudo -i -u postgres
```
In case the `systemctl enable` command failed, run this command to properly initialize a database file:
```
initdb -D /var/lib/postgres/data
```
Go ahead and rerun the systemctl command above.

Now we have to create a user with the following command:
```
createuser --interactive
```
It will ask for a username, if you input your linux username it will automatically grant you access with subsequent commands.  
note: you can safely ignore usernames and passwords referenced in other documents this way.

Go ahead and exit the postgre user shell:
```
exit
```
Finally we will create a database:
```
createdb myDatabaseName
```
And to verify everything works we open an interactive shell:
```
psql myDatabaseName
```
and then type `quit` to exit again

See the specific [PostgreSQL instructions](/PostgreSQL.md) for further information.

Resources
* Binary download: https://www.postgresql.org/download/linux/
* Arch wiki: https://wiki.archlinux.org/index.php/PostgreSQL
* How To Install and Use PostgreSQL on Ubuntu: https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-20-04

## MongoDB

### Installation
**Ubuntu**
```
sudo apt install mongodb
```
**Arch**

The AUR has a pre-build which can be installed with any AUR helper.
```
yay -S aur/mongodb-bin aur/mongodb-tools-bin
```
**Fedora**

Due to licensing Fedora chose not to include MongoDB in their repositories. So an additional step is required to get it installed.

```
sudo nano /etc/yum.repos.d/mongodb.repo
```

Copy paste this piece of text:
```
[mongodb-upstream]
name=MongoDB Upstream Repository
baseurl=https://repo.mongodb.org/yum/redhat/8Server/mongodb-org/4.4/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-4.4.asc
```
Key sequence to save and quit:
ctrl+x -> Y -> Enter

Then install as normal
```
sudo dnf install mongodb-org
```

### Setup
Once installed make sure the mongodb server is running (or at least exists) with:
```
systemctl status mongodb
```

If its not active use the following command to have it automatically start:
```
sudo systemctl enable --now mongodb
```
Repeat `systemctl status mongodb` to make sure it is in fact running this time.

note: the service file depends on your distribution, on Arch its `mongodb` and on Fedora its `mongod`.

Then run the mongo command to open the interactive shell
```
mongo
```
If everything went well you can type  
```
> quit()
```

to exit.

If it errors out saying the connection failed, reboot and try again.

See the specific [MongoDB instructions](/MongoDB.md) for further information.

Resources:
* Arch wiki: https://wiki.archlinux.org/index.php/MongoDB
* Binary downloads: https://www.mongodb.com/try/download/community
* How to Install MongoDB on Ubuntu: https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-from-the-default-apt-repositories-on-ubuntu-20-04
* MongoDB on Fedora: https://fedoramagazine.org/how-to-get-mongodb-server-on-fedora/
