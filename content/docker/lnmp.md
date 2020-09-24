---
title: "lnmp"
date: 2017-08-17 07:32
updated: 2016-08-23 18:07
log: "docker-cli-command"
---


## 格式 ##
$ docker images
$ docker pull ubuntu	# 拉取镜像
$ docker run -tid -p 8080:80 -p 3309:3306 -v ~/www:/var/www/html --name mylnmp ubuntu /bin/bash	# 端口映射、目录映射

> Ps: ubuntu 镜像名字要与docker hub 一致

$ docker exec -ti mylnmp /bin/bash	# 进入容器

## 容器内 ##

$ apt update 
$ apt upgrade
$ apt -y install nginx php-fpm mysql-client mysql-server vim

## 配置 PHP-FPM ##

$ vim /etc/php/7.4/fpm/pool.d/www.conf
cp /run/php/php7.4-fpm.sock
$ vim /etc/nginx/sites-enabled/default

> 替换 fastcgi_pass 配置

> 修改后的

        # pass PHP scripts to FastCGI server
        #
        location ~ \.php$ {
               include snippets/fastcgi-php.conf;
        #
        #       # With php-fpm (or other unix sockets):
                fastcgi_pass unix:/run/php/php7.4-fpm.sock;
        #       # With php-cgi (or other tcp sockets):
        #       fastcgi_pass 127.0.0.1:9000;
        }
        
        
## 配置 MySQL ##

1. root 账户远程登录访问

mysql> CREATE USER 'root'@'%' IDENTIFIED BY '11111111';
mysql> GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' WITH GRANT OPTION;
mysql> FLUSH PRIVILEGES;

2. mysql 配置允许外部访问

vim /etc/mysql/mysql.conf.d/mysqld.cnf

去掉这一行的注释
> #bind-address            = 127.0.0.1

3. 运行设置
> su: warning: cannot change directory to /nonexistent: No such file or directory
4. 执行下面两句
mysql> usermod -d /var/lib/mysql mysql
mysql> chown -R mysql:mysql /var/lib/mysql




