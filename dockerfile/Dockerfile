#https://stackoverflow.com/questions/35931053/cassandra-docker-unable-to-connect-through-jmx
FROM cassandra:3.11

RUN sed -i 's/JVM_OPTS="$JVM_OPTS -Dcom.sun.management.jmxremote.authenticate=true"/JVM_OPTS="$JVM_OPTS -Dcom.sun.management.jmxremote.authenticate=false"/g' /etc/cassandra/cassandra-env.sh

RUN sed -i '/password/d' /etc/cassandra/cassandra-env.sh