# PostgreSQL
```
sudo apt update
```
```
sudo apt install postgresql postgresql-contrib
```
```
apt install net-tools
```
```
sudo -u postgres psql postgres
```
```
 \password postgres
```
```
\q
```
```
nano /etc/postgresql/14/main/postgresql.conf
```
```
        listen_addresses = '*'
```
```
sudo nano /etc/postgresql/14/main/pg_hba.conf
```
```
 # Database administrative login by Unix domain socket
local   all             postgres                                peer
# TYPE  DATABASE        USER            ADDRESS                 METHOD
# "local" is for Unix domain socket connections only
local   all             all           trust
# IPv4 local connections:
host    all             all             127.0.0.1/32            md5
# IPv6 local connections:
host    all             all             ::1/128                 md5
# Allow replication connections from localhost, by a user with the
# replication privilege.
local   replication     all                                     md5
host    replication     all             127.0.0.1/32            md5
host    replication     all             ::1/128                 md5
host    all             all             0.0.0.0/0            md5
host    all             all             ::/0                 md5
```
```

```
```
sudo systemctl restart postgresql
sudo systemctl enable postgresql
```
```
sudo ufw allow 5432 
sudo ufw status
sudo netstat -plnt
```
```
curl https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo apt-key add
```
```
sudo sh -c 'echo "deb https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update'
```
```
sudo apt install pgadmin4
```
```
sudo /usr/pgadmin4/bin/setup-web.sh
```
```
sudo ufw allow 80
sudo ufw status
sudo netstat -plnt
```
```
ss -pnltue | grep 5432


