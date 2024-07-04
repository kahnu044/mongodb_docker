# MongoDB Docker

This repository contains a Docker Compose configuration for running a MongoDB instance.

## Prerequisites

Make sure you have the following installed on your system:

- Docker: [Install Docker](https://docs.docker.com/get-docker/)
- Docker Compose: [Install Docker Compose](https://docs.docker.com/compose/install/)

## Usage

1. Clone this repository to your local machine:

```bash
git clone https://github.com/kahnu044/mongodb_docker
cd mongodb_docker
```

2. Start the MongoDB container:

```bash
docker-compose up -d
```

The MongoDB container will now be running in the background.

## Connect to MongoDB

You can use MongoDB Compass or any other MongoDB client to connect to the running container.

```bash
Port: 27018
Username: root
Password: root
Hostname: localhost
```

### For mongoDB Compass you can use the following URL

```bash
# Connection string
mongodb://<Username>:<Password>@<Hostname>:<Port>

# Example
mongodb://root:root@localhost:27018

# Example for IP address
mongodb://root:root@172.11.29.21:27018
```

## Stopping and Cleaning Up

To stop the MongoDB container, run:

```bash
docker-compose down
```

This will stop and remove the container, but it will preserve the data due to the named volume.

## Customization

### Changing MongoDB Version:

To change the MongoDB version, update the `docker-compose.yml` file as follows:

```bash
# For latest
image: mongo:latest

# Mongodb 7.0
image: mongo:7.0

# For other version please check the Docker Hub
# https://hub.docker.com/_/mongo/tags
```

### Changing Credentials:

If you wish to change the MongoDB root username and password, edit the `docker-compose.yml` file:

```bash
environment:
MONGO_INITDB_ROOT_USERNAME: newusername
MONGO_INITDB_ROOT_PASSWORD: newpassword
```

### Hanging Port:

If you want to use a different port, update the ports section in `docker-compose.yml`.

```bash
ports:
   - 27018:27017

#Run over any Ip
ports:
   - 172.16.24.26:27018:27017
```

### Container Name:

The container is named `kahnu_mongodb_container` by default. You can change it by editing the `container_name` field in `docker-compose.yml`.

### Data Storage:

Data is stored in a named volume called `mongo_data`. If you want to change the volume name, update it in the `volumes` section.

## Author

[Kahnu Charan Swain](https://github.com/kahnu044)
