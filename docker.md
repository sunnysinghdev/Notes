# Docker

## docker run
> docker run --publish 8000:8080 --detach --name bb bulletinboard:1.0
```
--publish : forrward host port to docker port
--detach : run in background
--name : name of container
```
> docker rm --force `containername` (docker stop `name` and then remove docker rm `name`)

> docker ps --all (list containers)

> docker system df (Disk usage)

> docker system prune	(Remove unused data)
## Explore a running docker container:
>docker exec -it name-of-container bash

>docker-compose exec web bash

## Run Elastic search
> docker run --name elastic -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:7.9.2

## elastic Path
> `/usr/share/elasticsearch/data`