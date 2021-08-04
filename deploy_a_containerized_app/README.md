# 如何创建一个containerized app

## 下载docker
1. 创建[docker hub](https://hub.docker.com/) 账号
2. 安装[docker desktop](https://docker.com/)

## 大致步骤
![image](https://user-images.githubusercontent.com/10515333/127520321-884b83e4-77bc-49dc-83b7-8e35ec30ae5e.png)
1. 编写代码，创建依赖
2. 使用docker将所有东西打包成image
3. push到docker hub的repository上
4. 使用docker run 来跑这个image，作为一个container启动

```console
# 创建image nigelpulton改成你自己的docker hub 名字
docker image build -t nigelpulton/gsd:ctr

# 查看有哪些image 
docker image ls

# 修改image之后，push到registry
docker image push nigelpulton/gsd:ctr

```

* 去[docker hub repository](https://hub.docker.com/repositories) 上查看

* 跑image
```console
# 查看有哪些container
docker container ls

```

# Hosting a registry
* [docker hub](https://hub.docker.com) 上面有很多image，可以下载，也可以自己创建
* 一个image表达结构如下：
![image](https://user-images.githubusercontent.com/10515333/127522353-ee56352d-1aed-43b0-9504-ef0227a83a21.png)
1. 在docker hub下面创建reposity <your_docker_repo_name>
2. terminal docker login
docker login --username <your_docker_user_name>
```console
$ docker login --username imliuye 
Password: <enter your password>
Login Succeeded
```
