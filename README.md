# useful-commands


# DOCKER

upload docker image from one host to another

```bash
docker save {image_name} | bzip2 |pv | ssh {user}@{ip} docker load
```

remove docker container from docker-compose
```bash
docker-compose rm -f -s -v {container_name}
```

total size of docker images and volumes. 
```bash
docker system df 
docker system df -v #(list with size label)
```

remove docker volumes based on regex (AWK)
```bash
docker volume rm $(docker volume ls | awk '$2 ~ /^[0-9]/  {print $2}')
```

# Kubernetes

Exec container in pod
```bash
kubectl exec -ti ipengine-net-benchmark-488656591-gjrpc -c ipengine-net-benchmark-iperf-server /bin/bash
```