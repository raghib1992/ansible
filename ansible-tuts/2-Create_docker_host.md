## Create docker container for target host
```sh
docker run --name target-host1 -p 2525:22 -v /sys/fs/cgroup:/sys/fs/cgroup:ro --privileged -d abdennour/rhel:8-ssh
```

## Create ssh key localy
```sh
ssh-keygen -f docker
```

## login into docker
```sh
docker exec -ti target-host1 /bin/bash
```

## create user
```sh
useradd -m ansiuser
```
## create authorized_keys file
## copy public key into it

# ssh into docker 
```
ssh -i docker ansiuser@localhost -p 2525
```