# 使用Node Express APP

## 启动步骤：

1.  进入当前文件夹：
```console
cd first-app
```

2. build imagae
```
docker image build -t imliuye/docker_study:first-container .
```
`imliuye/docker_study:first-container`: 需要build的远程位置
`.` : 代表从当前目录获取Dockerfile并build

3. push to registory
https://hub.docker.com/repository/docker/imliuye/docker_study
```
$ docker image ls
REPOSITORY             TAG               IMAGE ID       CREATED          SIZE
imliuye/docker_study   first-container   ca5c76a332b5   45 minutes ago   124MB
$ docker image push imliuye/docker_study:first-container
```

4. run an image/container
```
# delete the image
docker image rm imliuye/docker_study:first-container
docker image ls

# 删除的原因：如果本地有，就直接找本地的image，如果本地没有，就去dockerhub找

docker container run -d --name web -p 8000:8080 \
imliuye/docker_study:first-container
#    web: 名字
#    -d: run in background
#    -p 8000:8080: 
#    -i interactive
#    -t terminal 
##        8000 前面8000是 本机的port，
        8080 后面的是container 的 por的8080

```

5. 访问localhost:8000

6.  container 操作:
```
docker container stop web 
docker container ls # 没有
docker dontainer ls -a
docker container start web
docker container stop web 

docker container rm web 
```

7. run in shell (you can debug in shell), ctrl+P+Q to exit
```

docker container run -it --name web -p 8000:8080 \
imliuye/docker_study:first-container

```

## 说明
* container和image的关系，就好比 vm template和vm的关系，或者是class和instance的关系


