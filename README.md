# Introduction

This repository is a fork of the [js-docker](https://github.com/TIBCOSoftware/js-docker) distribution that has been 
updated to include support for building, configuring, and running JasperReports Server **Community Edition** in containers.

<p align="center">
  <img src="https://github.com/Robinyo/js-docker/blob/master/login.png">
</p>

# Prerequisites

- [Docker Desktop](https://www.docker.com/products/docker-desktop)

# Installation

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
