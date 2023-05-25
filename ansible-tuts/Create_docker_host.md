## Create docker container for target host
```
docker run --name target-host1 -p 2525:22 -v /sys/fs/cgroup:/sys/fs/cgroup:ro --privileged -d abdennour/rhel:8-ssh
```


## Create ssh key localy
```
ssh-keygen
```

## login into docker
docker exec -ti target-host1 /bin/bash

## create user
useradd -m ansiuser

## create authorized_keys file
## copy public key into it

# ssh into docker 
```
ssh -i <private key file> ansiuser@localhost -p 2525
```