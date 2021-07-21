# docker-example
docker example

# docker安装zookeeper机群

## 拉取zookeeper镜像

* 注:latest是zookeeper版本,latest说明是最新版本.

```bash
docker pull zookeeper:latest
```

## docker-compose安装zookeeper集群
```bash
docker-compose -f zookeeper-cluster.yml up -d
```

## docker-composes删除zookeeper集群
```bash
docker-compose -f zookeeper-cluster.yml rm -sf
```
