#创建数据/日志目录 这里我们部署3个节点
mkdir /opt/es/data/{node0,node1,node2} -p
mkdir /opt/es/logs/{node0,node1,node2} -p
cd /opt/elasticsearch
#权限我也很懵逼啦 给了 privileged 也不行 索性0777好了
chmod 0777 /opt/es/data/* -R && chmod 0777 /opt/es/logs/* -R

#防止JVM报错
echo vm.max_map_count=262144 >> /etc/sysctl.conf
sysctl -p

#启动
docker-compose up -d
#查看
docker-compose ps