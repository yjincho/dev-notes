# PostgreSQL

## Install PostgreSQL on Ubuntu
```bash
$ sudo apt update
$ sudo apt install postgresql postgresql-contrib
```
```bash
$ sudo -u postgres psql -c "SELECT version();"
```

## Connect to PostgreSQL
_As the default configuration of Postgres is, a user called postgres is made on and the user postgres has full superadmin access to entire PostgreSQL instance running on your OS._
```bash
$ sudo -u postgres psql
```

_The above command gets you the psql command line interface in full admin mode._


_If authentication failed, refer to the below._
```
$ sudo vim /etc/postgresql/<version>/main/pg_hba.conf

# Database administrative login by Unix domain socket
local all postgres peer
```

## Creating user
```
$ sudo su - postgres -c "createuser <username>"
```

## Creating database
```
$ sudo su - postgres -c "createdb <dbname>"
```

## Giving the user a password
```
$ sudo -u postgres psql
postgres=# ALTER USER <username> WITH ENCRYPTED PASSWORD '<password>';
```

## Granting privileges on database
```
postgres=# GRANT ALL PRIVILEGES ON DATABASE <dbname> TO <username>;
```

## Backup
https://www.postgresqltutorial.com/postgresql-backup-database/
```
pg_dump -U postgres -W -F t <dbname> > backup_file.tar
```

## Restore
https://www.postgresqltutorial.com/postgresql-restore-database/
```
pg_restore --dbname=<dbname> --verbose backup_file.tar
```

## Allow external access
```
$ sudo vim /etc/postgresql/<version>/main/postgresql.conf

# what IP address(es) to listen on
listen_addresses = '*' 
```

```
$ sudo vim /etc/postgresql/<version>/main/pg_hba.conf

# IPv4 local connections:
host all all 0.0.0.0/0 md5
```
```
$ sudo /etc/init.d/postgresql restart
```

## Remove PostgreSQL on Ubuntu
```
$ dpkg -l | grep postgres
$ sudo apt-get --purge remove postgresql\*
```

```
$ rm -rf /etc/postgresql/
$ rm -rf /etc/postgresql-common/
$ rm -rf /var/lib/postgresql/
```

## Start/Stop PostgreSQL systemctl service
```
$ sudo systemctl start postgresql
$ sudo systemctl stop postgresql
```

# Reference

- [PostgreSQL Tutorial](https://www.postgresqltutorial.com/)