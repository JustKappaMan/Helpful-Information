# Configure PostgreSQL on Linux Mint

Solution found [here](https://stackoverflow.com/a/26735105)

---

Open the file `pg_hba.conf`. It's located in `/etc/postgresql/*version*/main`. Change this line at the bottom of the file, it should be the first line of the settings:

`local allpostgres peer` to `local allpostgres trust`

> [!NOTE]
> If you want to be able to connect with other users as well, you also need to change:

`local all all peer` to `local all all md5`

---

Restart the server:
```shell
sudo service postgresql restart
```

---

Login into psql and set your password:
```shell
psql -U postgres
```
```postgresql
ALTER USER postgres with password 'your-pass';
```

> [!NOTE]
> If you have other users, they will need a password as well:
```postgresql
ALTER USER my_user with password 'your-pass';
```

Then exit from psql.

---

Finally, change the content of `pg_hba.conf`:

`local all postgres trust` to `local all postgres trust`

And restart the server one more time:
```shell
sudo service postgresql restart
```

---

After restarting the server, the postgres user accepts the password that you chose:
```shell
psql -U postgres
```

> [!NOTE]
> Same now works for `my_user` if you added the user and password:
```shell
psql -d YOUR_DB_NAME -U my_user
```

---

Authentication methods details:
* `trust` - anyone who can connect to the server is authorized to access the database;
* `peer` - use client's operating system username as database username to access it;
* `md5` - password-base authentication.