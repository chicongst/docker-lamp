# LAMP Docker

Basic docker for LAMP | Linux Apche Mysql PHP

### Prerequisities


In order to run this container you'll need docker installed.

* [Windows](https://docs.docker.com/windows/started)
* [OS X](https://docs.docker.com/mac/started/)
* [Linux](https://docs.docker.com/linux/started/)

#### Step 

```shell
git clone https://github.com/chicongst/lamp_docker_base.git
cd lamp_docker_base
cp .env.example .env 
sudo docker-compose up --build
```
#### Access to container
```shell
# Access to server
sudo docker-compose exec server /bin/bash
# Access to database
sudo docker-compose exec mysql /bin/bash
```
