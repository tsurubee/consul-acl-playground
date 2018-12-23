# consul-acl-playground
Test environment for Consul ACL based on Docker

# Usage
## How to users Docker containers
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

## Bootstrapping ACL
Execute the following command on the Consul servers.  
```
/ # consul acl bootstrap
AccessorID:   8bd3c315-9155-57d7-a22f-451665f71154
SecretID:     4ec60a89-abaa-fda9-46c1-e6e174094a97
Description:  Bootstrap Token (Global Management)
Local:        false
Create Time:  2018-12-02 06:44:09.0256574 +0000 UTC
Policies:
   00000000-0000-0000-0000-000000000001 - global-management
```
Then, you can run the consul command with token like below.  
```
/ # consul members -token=4ec60a89-abaa-fda9-46c1-e6e174094a97
Node             Address           Status  Type    Build  Protocol  DC       Segment
consul-server-1  192.168.0.2:8301  alive   server  1.4.0  2         test-dc  <all>
consul-agent-1   192.168.0.3:8301  alive   client  1.4.0  2         test-dc  <default>
```

# Blog
- https://blog.tsurubee.tech/entry/2018/12/02/203015
