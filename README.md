## Commands

### Start a server in development mode
consul agent -dev

### List cluster member
consul members

### Install dig into linux alphine
apk -U add bind-tools

### Query to find IPs and services registred into consul
dig @localhost -p 8600 consul01.node.consul

### Up a consul server
consul agent -server -bootstrap-expect=3 -bind=172.20.0.3 -data-dir=/var/lib/consul -config-dir=/etc/consul.d

#### -bootstrap-expect
Numbers of expected servers

#### -node
Node name 

#### -bind
Current IP

#### -data-dir 
Directory where consul store its files

#### -config-dir
Directory where consul store its configurations 

### Join servers
consul join 172.20.0.2

### Up a consul client
consul agent -bind=172.20.0.5 -data-dir=/var/lib/consul -config-dir=/etc/consul.d -retry-join=172.20.0.2

#### -retry-join
After up the agent join into a cluster

### Update services
consul reload

### Find service node
consul catalog nodes -service nginx

### List all nodes
consul catalog nodes -detailed

### Generate key to use encrypt
consul keygen
