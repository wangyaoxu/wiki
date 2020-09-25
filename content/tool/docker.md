---
title: "Docker"
date: 2015-11-08 12:34
updated: 2017-09-14 15:10
collection: "虚拟化"
log: "增加 docker hub 使用 mirror"
---

[TOC]

[Docker](https://www.docker.com/) Build, Ship, Run; An open platform for distributed applications for developers and sysadmins

## 前言 ##

> docker 虚拟化

入门参考:

* [Docker - Get Started](http://docs.docker.com/linux/started/)
* [Docker - Docs](https://docs.docker.com/)

实践：

* [Dockerfile Best Practices](http://crosbymichael.com/dockerfile-best-practices.html) / [Dockerfile最佳实践](http://dockone.io/article/131)
* [Best practices for writing Dockerfiles](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)

## 基础 ##
### Image ###

```bash
docker search ubuntu
docker pull hello-world
docker run hello-world

docker images 
docker rmi -f ubuntu
docker rmi `docker image -q`	# 批量删除
```

### Container ###

```bash
docker run -tid -p 8080:80 -p 3309:3306 -v ~/www:/var/www/html --name mylnmp ubuntu /bin/bash
# ps： ubuntu 镜像的名字，要与docker hub 一致
# -i 表示允许我们对容器进行操作 -t 表示在新容器内指定一个为终端 -d 表示容器在后台执行 

docker start ContainerId/name
docker restart ContainerId
docker stop ContainerId
docke kill ContainerId

# 查看容器
docker ps 
docker ps -a
docker port mylnmp # 查看端口映射

docker logs mylnmp

# 删除
docker rm -f xx

# 登录
docker exec -it xx /bin/bash 
```
