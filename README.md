# PHP 5.6 + Apache + MySQL 5.7 (Ubuntu 20.04 based image)

## Introduction

This repository contains a Docker project that allows you to run PHP 5.6 + Apache + MySQL 5.7 using Docker. It provides a convenient way to set up a development environment with specific versions of PHP, Apache, and MySQL.

## Available PHP Extensions

The following PHP extensions are available in this Docker project:

- fpm
- iconv
- pdo-mysql
- curl
- mbstring
- bcmath
- xml
- soap
- intl
- sockets
- zip
- gd
- mcrypt
- sqlite3
- cli
- common
- json
- mysql

## Timezone

The current timezone set for this project is `America/Sao_Paulo`. If needed, you can easily change it according to your preferences.

## Supervisor

This project uses the Supervisor tool for managing and keeping services running smoothly within the Docker environment.

## Getting Started

To get started with this Docker project, follow these steps:

1. Install Docker on your system if you haven't already. You can find installation instructions on the [official Docker website](https://www.docker.com/).

2. Clone this repository to your local machine:

```bash
git clone git@github.com:agostinhodev/php5.6-apache-mysql-using-docker.git
```

3. Change directory:

```bash
cd php5.6-apache-mysql-using-dockerg
```

4. Run it using docker-compose

```bash
docker-compose up -d --build
```