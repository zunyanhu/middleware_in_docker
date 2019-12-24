# 使用
1. `docker-compose up -d`启动所有容器
2. `docker-compose exec cli bash`进入cli容器，然后执行命令`redis-cli --cluster create 10.0.0.2:6379 10.0.0.3:6379 10.0.0.4:6379 10.0.0.5:6379 10.0.0.6:6379 10.0.0.7:6379 --cluster-replicas 1`，创建集群
3. `docker-compose exec redis1 redis-cli cluster nodes`查看集群状态