```
docker swarm init
docker service create --name web -p 8080:8080 --replicas 3 imliuye/docker_study:first-container
# 访问localhost:8080 刷新，发现每次的container id都不一样
docker container ls
docker service ps web
docker service scale web=10
docker container ls
```

