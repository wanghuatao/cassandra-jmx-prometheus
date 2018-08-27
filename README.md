# cassandra-jmx-prometheus

**build cassandra with jmx**
cd dockerfile
sudo docker build -t yuzhonglele/cassandra:3.11 . 


**run cassandra**

docker run  --restart=always  --name cassandra -d \
 -p 9042:9042  -p 7000:7000 -p 7199:7199 -p  9160:9160 \
-v /data/cadata:/var/lib/cassandra \
-e CASSANDRA_BROADCAST_ADDRESS=<**your ip**> \
-e CASSANDRA_CLUSTER_NAME=mycluster  \
-e LOCAL_JMX=no \
-e JVM_EXTRA_OPTS=-Djava.rmi.server.hostname=127.0.0.1 \
 yuzhonglele/cassandra:3.11



**run cassandra prometheus export**
cd prometheus
sudo docker run   -v $PWD/config.yml:/etc/cassandra_exporter/config.yml --net=host    criteord/cassandra_exporter:latest
