---
layout: default
---

# Docker Compose Basics
## Why
- configure relationships between containers
- save our docker container run settings in easy-to-read file
- create one-liner developer environment startups
## Components
Comprised of 2 separate but related things
1. YAML-formatted file that describes our solution options for:
  - containers
  - networks
  - volumes
2. A CLI tool docker-compose used for local dev/test automation with those YAML files
## docker-compose.yml
- Compose YAML format has it's own versions: 1, 2, 2.1, 3, 3.1
- YAML file can be used with `docker-compose` command for local docker automation or..
- With `docker` directly in production with Swarm (as of v1.13)
- `docker-compose --help`
- `docker-compose.yml` is default filename, but any can be used with `docker-compose -f`

## Template
```yml
version: '3.1'  # if no version is specificed then v1 is assumed. Recommend v2 minimum

services:  # containers. same as docker run
  servicename: # a friendly name. this is also DNS name inside network
    image: # Optional if you use build:
    command: # Optional, replace the default CMD specified by the image
    environment: # Optional, same as -e in docker run
    volumes: # Optional, same as -v in docker run
  servicename2:

volumes: # Optional, same as docker volume create

networks: # Optional, same as docker network create

```
## Example 1
This create a Jekyll service.
```yml
version: '2'

# same as 
# docker run -p 80:4000 -v $(pwd):/site bretfisher/jekyll-serve

services:
  jekyll:
    image: bretfisher/jekyll-serve
    volumes:
      - .:/site
    ports:
      - '80:4000'

```
## Example 2
This creates a wordpress service.
```yml
version: '2'

services:

  wordpress:
    image: wordpress
    ports:
      - 8080:80
    environment:
      WORDPRESS_DB_HOST: mysql
      WORDPRESS_DB_NAME: wordpress
      WORDPRESS_DB_USER: example
      WORDPRESS_DB_PASSWORD: examplePW
    volumes:
      - ./wordpress-data:/var/www/html

  mysql:
    image: mariadb
    environment:
      MYSQL_ROOT_PASSWORD: examplerootPW
      MYSQL_DATABASE: wordpress
      MYSQL_USER: example
      MYSQL_PASSWORD: examplePW
    volumes:
      - mysql-data:/var/lib/mysql

volumes:
  mysql-data:
	
```
## Useful Links
- [docker-compose.yml sample for Ghost (A web log) with load-balanced MySQL](https://github.com/BretFisher/udemy-docker-mastery/blob/master/compose-sample-1/compose-3.yml)
- [Compose file version 3 reference](https://docs.docker.com/compose/compose-file/)
# Docker Compose CLI
- CLI tool comes with Docker for Windows/Mac, but separate download for Linux
- Not a production-grade tool but ideal for local development and test
- Two most common commands are
	- `docker-compose up` # setup volumes/networks and start all containers
	- `docker-compose down` # stop all containers and remove cont/vol/net
- If all your projects had a `Dockerfile` and `docker-compose.yml` then "new developer onboarding" would be:
	- `git clone github.com/some/software`
	- `docker-compose up`

## Demo
Clone https://github.com/BretFisher/udemy-docker-mastery/tree/master/compose-sample-2
`docker-compose up` for running in the foreground
`docker-compose up -d` for running in the background
`docker-compose logs` to see the log
`docker-compose ps` to see list of containers
`docker-compose top` to see list of processes
`docker-compose down` to stop and remove the service
# Assignment: Writing A Compose File
- Build a basic compose file for a Drupal content management system website. Docker Hub is your friend
- Use the `drupal` image along with the `postgres` image
- Use ports to expose Drupal on 8080 so you can localhost:8080
- Be sure to set `POSTGRES_PASSWORD` for postgres
- Walk though Drupal setup via browser
- Tip: Drupal assumes DB is `localhost`, but it's service name
- Extra Credit: Use volumes to store Drupal unique data

## Answer
```yml
version: '2'

services: 
  drupal:
    image: drupal
    ports: 
      - 8080:80
    volumes: 
      - drupal-modules:/var/www/html/modules
      - drupal-profiles:/var/www/html/profiles
      - drupal-sites:/var/www/html/sites
      - drupal-themes:/var/www/html/themes
  postgres:
    image: postgres
    environment: 
      - POSTGRES_PASSWORD=yourpasswd

volumes: 
  drupal-modules:
  drupal-profiles:
  drupal-sites:
  drupal-themes:
```