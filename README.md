## LAMP based on Docker

#### Environment consist of Docker containers where:
- webserver - Apache / PHP 7.3 / Composer
- mysql - MySQL 5.7

To build run:
```
docker-compose up --build -d
```
Environment builds with default configuration. 

To set your own config rename `sample.env` to `.env` and set required values in it.