# Docker MySQL Setup

A Docker-based MySQL database setup using Docker Compose for easy deployment and management.

## Description

This repository provides a simple and efficient way to run a MySQL database instance using Docker containers. It's designed to work with an external Docker network (`my_infra_network`) for easy integration with other services.

## Features

- MySQL database container
- Environment variable configuration
- Persistent data storage using volumes
- Network integration with external Docker network
- Easy port mapping configuration

## Prerequisites

- Docker
- Docker Compose
- An existing Docker network named `my_infra_network`

## Setup

1. Clone this repository:
```bash
git clone <repository-url>
cd docker_mysql_old_2
```

2. Create a `.env` file with the following variables:
```
MYSQL_HOST=localhost
MYSQL_USER=your_user
MYSQL_PASSWORD=your_password
MYSQL_ROOT_PASSWORD=your_root_password
DB_PORT=3306
```

3. Create the external network if it doesn't exist:
```bash
docker network create my_infra_network
```

4. Start the database:
```bash
docker-compose up -d
```

## Configuration

The database configuration is managed through environment variables defined in your `.env` file:

- `MYSQL_HOST`: Database host
- `MYSQL_USER`: MySQL user
- `MYSQL_PASSWORD`: MySQL user password
- `MYSQL_ROOT_PASSWORD`: MySQL root password
- `DB_PORT`: Port to expose the database on the host machine

## Data Persistence

Database data is persisted in the `./database/data` directory on your host machine, which is mounted to `/var/lib/mysql` in the container.

## Stopping the Database

```bash
docker-compose down
```

To remove the data volume as well:
```bash
docker-compose down -v
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
