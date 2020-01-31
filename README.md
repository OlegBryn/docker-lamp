## LAMP based on Docker

#### Environment consists of Docker containers where:
- webserver - Apache / PHP 7.3 / Composer
- mysql - MySQL 5.7

To build run:
```
docker-compose up --build -d
```
Environment builds with default options 

To change default values, you should set required params in `sample.env` file and rename it to `.env` BEFORE building or RESTART else.
```
docker-compose restart webserver mysql
```
