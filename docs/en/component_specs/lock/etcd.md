# Etcd

## metadata fields
Example: configs/config_lock_etcd.json

| Field | Required | Description |
| --- | --- | --- |
| endpoints | Y | etcd server address, multiple address use `;` separate |
| dialTimeout | N | dialTimeout is the timeout for failing to establish a connection in seconds. default: 5 |
| username | N | etcd auth username |
| password | N | etcd auth password |
| keyPrefix | N | lock key prefix in etcd, default: `/layotto/` |
| tlsCert | N | tls certificate path |
| tlsCertKey | N | tls certificate key path |
| tlsCa | N | tls ca path |

## How to start etcd
If you want to run the etcd demo, you need to start a etcd server.
command：

download etcd from `https://github.com/etcd-io/etcd/releases` （You can also use docker.）

start：
````shell
./etcd
````

default listen address `localhost:2379`

## Run layotto

````shell
cd ${projectpath}/cmd/layotto
go build
````
>If build reports an error, it can be executed in the root directory of the project `go mod vendor`

Execute after the compilation is successful:
````shell
./layotto start -c ../../configs/config_lock_etcd.json
````

## Run Demo

````shell
cd ${projectpath}/demo/lock/etcd/
 go build -o client
 ./client
````
