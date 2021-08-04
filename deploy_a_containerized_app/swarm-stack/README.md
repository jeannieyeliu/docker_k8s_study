# Swarm stack

Python flask app:
- stores counter in redis
- returns count and hostname of contriner servicing request

# console
```
cd swarm-stack
docker image build -t imliuye/docker_study:swarm-stack .
docker image push imliuye/docker_study:swarm-stack
# https://hub.docker.com/repository/docker/imliuye/docker_study
docker stack deploy -c docker-compose.yml counter # counter is name of the app
docker stack ls
docker stack ps counter
# localhost:5000 , refress

change replicas: 5 in yml file
docker stack ps counter
docker stack rm counter
```
