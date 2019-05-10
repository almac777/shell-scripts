# Just some useful scripts

When working with docker.

# git

Added some scripts to automate setting up some of my favorite git aliases etc.

# PSQL

Since this is something I like to forget:

```
psql -U <username> [-d <database-name>] --password
# Create user + password + db and grant all privileges
CREATE USER <new-user> WITH PASSWORD '<new-password>';
CREATE DATABASE databasename
GRANT ALL PRIVILEGES ON DATABASE "<new-database>" TO <new-user>;
```

# Docker

Unfortunately I keep forgetting how exactly to do some details with docker. The scripts here are just diff HOWTOs I have and will accumulate over time. Trying to sort them by categories.

One could also simply use portainer.io or something like that.

## Docker After Install

https://docs.docker.com/install/linux/linux-postinstall/

`sudo groupadd docker`

`sudo usermod -aG docker $USER`

`docker run hello-world`

If an error occurs:

`sudo chown "$USER":"$USER" /home/"$USER"/.docker -R`

`sudo chmod g+rwx "$HOME/.docker" -R`

## Docker Containers

This is quite handy whenever you have to import a file, after you've already built a container.

```
(docker exec -i <CONTAINER> sh -c "cat > <OUTPUT-FILENAME-CONTAINER>") < <INPUT-FILENAME-HOSTSYSTEM>
# optional: docker exec -it <CONTAINER> bash and wget the file.
```


## Docker Networks

Create a docker network and give it a name.
Other containers can be plugged into this network, so they can find each other via IPs.

```
docker network create --subnet <SUBNET, e.g.: 172.19.0.0/16> docker-subnet
```

