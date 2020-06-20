<h1 align="center">Container deployment of JasperReports Server Community Edition</h1>

<p align="center">
  <img src="https://github.com/Robinyo/js-docker/blob/login.png">
</p>

# Table of contents

1. [Introduction](#introduction)
1. [Prerequisites](#prerequisites)
1. [Installation](#installation)
   1. [Get the JasperReports Server container configuration](#get-the-js-docker-dockerfile-and-supporting-resources)
   1. [js-docker Repository structure](#the-installed-repository-structure)
   1. [Building JasperReports Server images](#building-jasperreports-server-images)
     1. [Prepare the resources for the images](#prepare-the-resources-for-the-images)
     1. [docker build time environment variables](#docker-build-time-environment-variables)
     1. [Build the images](#build-the-images)
1. [docker run time environment variables](#docker-run-time-environment-variables)
1. [Configuring JasperReports Server with volumes](#configuring-jasperreports-server-with-volumes)
   1. [Using data volumes](#using-data-volumes)
   1. [JasperReports Server use of volumes](#jasperreports-server-use-of-volumes)
   1. [Setting volumes](#setting-volumes)
   1. [Paths to data volumes on Mac and Windows](#paths-to-data-volumes-on-mac-and-windows)
1. [Initializing the JasperReport Server Repository](#initializing-the-jasperreport-server-repository)
   1. [Using a pre-existing database server](#using-a-pre-existing-database)
   1. [Using a database container](#using-a-database-container)
1. [Building and running with docker-compose](#building-and-running-with-docker-compose)
1. [Import and Export for the JasperReports Server repository](#import-and-export) 
   1. [Export from a JasperReports Server repository](#exporting-to-a-jasperreports-server-repository)
   1. [Import into a JasperReports Server repository](#importing-from-a-jasperreports-server-repository)
1. [JasperReports Server logs](#jasperreports-server-logs)
1. [Logging in to JasperReports Server](#logging-in-to-jasperreports-server)
1. [Troubleshooting](#troubleshooting)
   1. [Unable to download phantomjs](#unable-to-download-phantomjs)
   1. ["No route to host" error on a VPN/network with mask](#-no-route-to-host-error-on-a-vpn-or-network-with-mask)
   1. [`docker volume inspect` returns incorrect paths on MacOS X](#-docker-volume-inspect-returns-incorrect-paths-on-macos-x)
   1. [`docker-compose up` fails with permissions error](#-docker-compose-up-fails-with-permissions-error)
   1. [Connection to repository database fails](#connection-to-repository-database-fails)
1. [Docker documentation](#docker-documentation)

# Introduction

This repository is a fork of the js-docker distribution that has been updated to include support for building, 
configuring, and running TIBCO JasperReports&reg; Server Community Edition in containers.

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
