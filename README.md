# Introduction

This repository is a fork of the [js-docker](https://github.com/TIBCOSoftware/js-docker) distribution that has been 
updated to include support for building, configuring, and running TIBCO JasperReports Server **Community Edition** in 
containers.

<p align="center">
  <img src="https://github.com/Robinyo/js-docker/blob/master/login.png">
</p>

# Prerequisites

- [Docker Desktop](https://www.docker.com/products/docker-desktop)

# Clone the project

Use Git to clone the repository:

```
$ git clone https://github.com/Robinyo/js-docker
$ cd js-docker
```

[Download](https://community.jaspersoft.com/project/jasperreports-server/releases) the Community Edition of 
JasperReports Server and place it in the `resources` directory.

Unpack the zip archive:

```
# chmod 755 unpackWARInstaller-ce.sh
./unpackWARInstaller-ce.sh
```

[Download](https://phantomjs.org/download.html) the Linux 64-bit version of PhantomJS and place it in the `resources` 
directory.

[Download](https://jdbc.postgresql.org/download.html) the PostgreSQL JDBC driver and place it in the `resources` 
directory.


### Serve the applications

To run a multi-container application with the Docker CLI, you use the `docker-compose up` command. 
This command uses the project's [docker-compose.yml] file to deploy a multi-container application:

```
docker-compose up -d
```

The PostgreSQL, pgAdmin and JasperReports Server containers may take a minute or two to startup. 

You can check the status of the containers using the following command:

```
docker-compose ps
```

To check the logs inside your container:

```
dodocker container logs postgres
docker container logs pgadmin
docker container logs jasperreports-server
docker container logs jasperreports-server-cmdline
```

You can stop the containers using the following command:

```
docker-compose down -v
```
