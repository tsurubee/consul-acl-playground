# consul-acl-playground
Test environment for Consul ACL based on Docker

# Usage
Start up containers.  
```
$ docker-compose up -d
Starting consul-acl-playground_consul-server_1 ... done
Starting consul-acl-playground_consul-agent_1  ... done
```
To enter inside the launched container, execute the following command.  
```
$ docker exec -it consul-acl-playground_consul-server_1 /bin/ash
```
To see the log of Consul agent, execute the following command.  
```
$ docker logs -f consul-acl-playground_consul-server_1
```

# Blog
- https://blog.tsurubee.tech/entry/2018/12/02/203015
