
### Login on postgres user

~~~
sudo su -l postgres
~~~

### Initialize databases with postgres user

~~~
initdb -D /var/lib/postgres/data
~~~

### Create new user

~~~
createuser --interactive
~~~

Create database of user:
~~~
CREATE DATABASE <username>
~~~

Make a user owner of a database:
```
ALTER DATABASE your_database_name OWNER TO your_username;
```

## Security configuration

Edit file `var/lib/postgres/data/pg_hba.conf`:
```
# TYPE  DATABASE        USER            ADDRESS                 METHOD

# "local" is for Unix domain socket connections only
local   all             all                                     scram-sha-256
```

Give user a password:
```
ALTER USER your_username WITH PASSWORD 'your_new_password';
```



