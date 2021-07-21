## docker-example
docker example


## docker basic command

```bash
1、docker pull image
2、docker run exec -itd --name name -p port:port images:version 
3、docker ps
4、docker images 
5、docker logs
6、docker kill container id
7、docker stop container id 
8、docker rm container id
9、docker rmi images
x、docker start container id
```

### docker ps command 

```bash
docker ps [OPTIONS]
```

```bash
Options:
  -a, --all             Show all containers (default shows just running) 显示所有的容器,包含未运行的.
  -f, --filter filter   Filter output based on conditions provided 根据条件过滤显示内容(name=value). 
      --format string   Pretty-print containers using a Go template 指定返回值的模版文件.
  -n, --last int        Show n last created containers (includes all states) (default -1) 列出最近创建的N个容器.
  -l, --latest          Show the latest created container (includes all states) 显示最近创建的容器.
      --no-trunc        Don't truncate output 不截断输出.
  -q, --quiet           Only display container IDs 静默模式,只显示容器ID.
  -s, --size            Display total file sizes 显示总文件大小.
```

### docker ps instance

```bash
# gaoxinzhong @ gaoxinzhongdeMacBook-Pro in ~ [11:25:12] 
$ docker ps 
CONTAINER ID   IMAGE                       COMMAND                  CREATED      STATUS        PORTS                                                  NAMES
7a6cefa317c4   hhyo/archery:1.8.1          "dockerize -wait tcp…"   5 days ago   Up 18 hours   0.0.0.0:9123->9123/tcp, :::9123->9123/tcp              archery
a9278bd253ad   hanchuanchuan/goinception   "/usr/local/bin/dumb…"   5 days ago   Up 18 hours   4000/tcp                                               goinception
f0a813cc3990   mysql:5.7                   "docker-entrypoint.s…"   5 days ago   Up 18 hours   0.0.0.0:3306->3306/tcp, :::3306->3306/tcp, 33060/tcp   mysql
a99d4dd00c86   hhyo/inception              "/bin/sh -c 'nohup /…"   5 days ago   Up 18 hours   6669/tcp                                               inception
742f70362317   redis:5                     "docker-entrypoint.s…"   5 days ago   Up 18 hours   6379/tcp                                               redis
```
* CONTAINER ID 容器ID
* IMAGE 使用的镜像
* COMMAND 启动容器时运行的命令
* STATUS 容器状态
   * created 已创建
   * restarting 重启中
   * running 运行中
   * removing 迁移中
   * paused 暂停中
   * exited 停止
   * dead 死亡
* PORTS 容器的端口和本机端口映射(tcp/udp)
* NAMES 容器名称

### docker exec command

```bash
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
```

```bash
Options:
  -d, --detach               Detached mode: run command in the background
      --detach-keys string   Override the key sequence for detaching a container
  -e, --env list             Set environment variables
      --env-file list        Read in a file of environment variables
  -i, --interactive          Keep STDIN open even if not attached
      --privileged           Give extended privileges to the command
  -t, --tty                  Allocate a pseudo-TTY
  -u, --user string          Username or UID (format: <name|uid>[:<group|gid>])
  -w, --workdir string       Working directory inside the container
```

## docker install zookeeper cluster

### pull zookeeper images

* 注:latest是zookeeper版本,latest说明是最新版本.

```bash
docker pull zookeeper:latest
```

### docker-compose install zookeeper cluster

```bash
docker-compose -f zookeeper-cluster.yml up -d
```

### docker-compose remove zookeeper cluster

```bash
docker-compose -f zookeeper-cluster.yml rm -sf
```
