用法：
直接执行 sudo docker-compose up -d，集群搭建成功。目前只对 zoo1 的数据进行了容器磁盘挂载。

检查集群状态:
docker-compose ps

# check cluster status
docker run -it --rm \
    --link zoo1:zk1 \
    --link zoo2:zk2 \
    --link zoo3:zk3 \
    --net service-zookeeper_zoo-net \
    zookeeper:3.5.5 zkCli.sh -server zk1:2181,zk2:2181,zk3:2181
进入控制台后，先按一个回车，然后，ls /，可开始查看 zookeeper 集群存储的数据。