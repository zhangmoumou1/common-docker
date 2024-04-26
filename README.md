# docker构建安装mysql和redis

## 环境准备
安装完成docker和docker-compose

将`env.template`改为`.env`，可以使用命令
```bash
mv env.template .env
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
删除容器
```bash
docker-compose down
```

## 默认配置
mysql账密：root  root123456
redis秘钥：root123456