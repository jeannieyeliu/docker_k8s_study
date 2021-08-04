# 一个简单的counter app， 
使用了：
* docker compose,
* flask, 
* 计算web visit数量，
* 储存在Redic backend

# 打包compose
```
$ cd multi-container
docker-compose up -d
# -d: detach to background
# get .yaml file and compose it.
```
* 查看结果，看build了哪些image
```
$ docker container ls
CONTAINER ID   IMAGE                    COMMAND                  CREATED         STATUS         PORTS                                       NAMES
f1daa387f0de   redis:alpine             "docker-entrypoint.s…"   2 minutes ago   Up 2 minutes   6379/tcp                                    multi-container_redis_1
7da16716732d   multi-container_web-fe   "python app.py pytho…"   2 minutes ago   Up 2 minutes   0.0.0.0:5000->5000/tcp, :::5000->5000/tcp   multi-container_web-fe_1

```
* 访问 http://localhost:5000/
* container stop:
```
docker-compose down
```

# 创建SWARM
1. 创建docker service
```
# only available in swarm mode. must initiate a swarm
docker service create
```
