# big-data-docker

## openjdk11

```shell
docker build -t openjdk11 ./openjdk
```

## hadoop

```shell
# build image
docker compose build
# start up hadoop and hive services
docker compose up
```



## spark

```shell
docker build -t spark3 ./spark3
docker run --name spark3 --network big_data_default -ti spark3 bash
```

## port

| port  | service name    |
| ----- | --------------- |
| 50070 | namenode web ui |
| 50075 | datanode web ui |
| 4040  | spark ui        |



