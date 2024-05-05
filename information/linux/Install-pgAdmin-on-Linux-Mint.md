# Install pgAdmin on Linux Mint

Solution found [here](https://forums.linuxmint.com/viewtopic.php?t=393497).

---

Go to [PostgreSQL FTP server](https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/jammy/dists/pgadmin4/main/binary-amd64/) and find pgAdmin binaries there.

---

Install these packages in this order:
* `libpq`
* `libpq-dev`
* `pgadmin4-server`
* `pgadmin4-desktop`