---
title: "docker cli command"
date: 2017-08-17 07:32
updated: 2016-08-23 18:07
log: "docker-cli-command"
---


## 格式 ##

docker run -tid ubuntu
> -i 表示允许我们对容器进行操作 -t 表示在新容器内指定一个为终端 -d 表示容器在后台执行 
docker run -tid --name hd ubuntu /bin/bash

docker start ContainerId
docker restart ContainerId
docker stop ContainerId
docke kill ContainerId

## 查看容器 ##
docker ps 
docker ps -a
docker port xx # 查看端口映射

docker logs xx

## 删除 ##
docker rm -f xx

## 登录 ##
docker exec -it xx /bin/bash 

