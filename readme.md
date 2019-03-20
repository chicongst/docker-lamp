# CC Docker

Just a basic docker

## Getting Started

These instructions will cover usage information and for the docker container 

### Prerequisities


In order to run this container you'll need docker installed.

* [Windows](https://docs.docker.com/windows/started)
* [OS X](https://docs.docker.com/mac/started/)
* [Linux](https://docs.docker.com/linux/started/)

### Install project example

```shell
git clone https://github.com/chicongst9x/laravel-auth-api.git
mv laravel-auth-api cc_admin
cd cc_admin
chmod -R 777 storage/
cp .env.example .env
```

### Install docker

#### Step by step

Step 1

```shell
git clone https://github.com/chicongst9x/cc_docker.git
```

Step 2

```shell
cd cc-docker
cp .env.example .env 
sudo docker-compose up --build
```
Step 3

```shell
sudo docker-compose exec admin composer install
sudo docker-compose exec admin php artisan key:generate
sudo docker-compose exec admin php artisan jwt:secret
sudo docker-compose exec admin php artisan migrate
```

#### Environment Variables

* `MYSQL_CONTAINER_USER`  - mysql
* `MYSQL_CONTAINER_GROUP` - mysql
* `ADMIN_SOURCE_PATH`     - /var/www/html/cc_admin

## Authors

* **Chicongst** - *Work* - [Github](https://github.com/chicongst9x)

See more (https://github.com/chicongst9x/laravel-auth-api)
