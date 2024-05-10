# docker构建安装mysql和redis

🎉 docker部署详细文档：<a href="http://zhangyanc.club/article/docker_mysql_redis/">点击查阅</a>

## 环境准备
1、安装完成docker和docker-compose

若是ubuntu系统可简介此文章，[http://zhangyanc.club/article/docker_docker-compose/](http://zhangyanc.club/article/docker_docker-compose/)

2、将`env.template`改为`.env`，可以使用命令
```bash
mv env.template .env
```
3、mysql下创建`data`文件夹
```bash
mkdir ./mysql/data
```
## 容器部署
### 1、下载镜像
下载mysql镜像
```bash
docker pull mysql:5.7
```
下载redis镜像
```bash
docker pull redis:alpine
```
### 2、进行部署
创建容器
```bash
docker-compose up -d
```
执行以下命令，看到State为`up`状态说明启动成功，可以连接mysql和redis验证以下
```bash
root@VM-0-5-ubuntu:~/dockers/common-docker# docker-compose up -d
WARNING: Some networks were defined but are not used by any service: frontend
Creating network "common-docker_backend" with driver "bridge"
Creating redis ... done
Creating mysql ... done
root@VM-0-5-ubuntu:~/dockers/common-docker# docker-compose ps
WARNING: Some networks were defined but are not used by any service: frontend
Name               Command               State                 Ports              
----------------------------------------------------------------------------------
mysql   docker-entrypoint.sh mysqld      Up      0.0.0.0:3306->3306/tcp, 33060/tcp
redis   docker-entrypoint.sh sh -c ...   Up      0.0.0.0:6379->6379/tcp  
```

删除容器
```bash
docker-compose down
```

## 默认配置
mysql账密：root  root123456

redis秘钥：root123456