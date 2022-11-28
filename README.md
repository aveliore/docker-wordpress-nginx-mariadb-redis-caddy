# Dockerized WordPress, NGINX, MariaDB and Redis stack with Caddy as a reverse-proxy
Docker-compose configuration files and instructions for running a stack consisting of: 
* **WordPress** - most popular open-source CMS software
* **NGINX** - high performance webserver 
* **MariaDB** - MySQL database management system 
* **Redis** - in-memory datastore for caching 
* **Caddy** - webserver with auto HTTPS, used as reverse-proxy 

## How to use? 

### Requirements 
* **SSH access** to a host running a **modern Linux distribution**
* A **domain** with A record pointing to the host 

### 1. Install Docker and Docker Compose 
Install Docker and Docker compose on your host or make sure they are installed and updated to recent versions. Some guides are available on the [Docker Docs website](https://docs.docker.com/engine/install/).

### 2. Download this repository 
```
git pull https://github.com/aveliore/docker-wordpress-nginx-mariadb-redis-caddy.git  
```

### 3. Create the Docker networks 
In this guide we will create the following Docker networks: 
* **wppublicnet** - public network with CIDR 192.168.1.0/24 
* **wpprivatenet** - private network with CIDR 10.0.1.0/24 

```
sudo docker network create --driver=bridge --ip-range=192.168.1.0/24 --gateway=192.168.1.1 --attachable wppublicnet
```
```
sudo docker network create --driver=bridge --ip-range=10.0.1.0/24 --gateway=10.0.1.1 --attachable --internal wpprivatenet
```
You can change the IP addresses, gateways and naming if needed. 


### 4. Modify the configuration files 

### 5. Run the stack 
