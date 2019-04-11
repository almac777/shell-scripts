# Just some useful scripts

When working with docker.

# PSQL

Since this is something I like to forget:

```
psql -U <username> --password
# Create user + password + db and grant all privileges
CREATE USER <new-user> WITH PASSWORD '<new-password>';
CREATE DATABASE databasename
GRANT ALL PRIVILEGES ON DATABASE "<new-database>" TO <new-user>;
```

# Docker Networks

Create a docker network and give it a name

```
docker network create --subnet 172.19.0.2/16 default-database
```
