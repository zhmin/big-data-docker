FROM openjdk11

WORKDIR /opt
RUN apt-get update && apt-get install -y wget && wget https://mirrors.tuna.tsinghua.edu.cn/apache/hive/hive-2.3.9/apache-hive-2.3.9-bin.tar.gz

RUN tar -xzf apache-hive-2.3.9-bin.tar.gz
COPY hive-env.sh  apache-hive-2.3.9-bin/conf/
COPY hive-site.xml  apache-hive-2.3.9-bin/conf/

RUN wget https://mirrors.tuna.tsinghua.edu.cn/apache/hadoop/common/hadoop-2.10.1/hadoop-2.10.1.tar.gz
RUN tar -xzf hadoop-2.10.1.tar.gz
COPY core-site.xml /opt/hadoop-2.10.1/etc/hadoop/core-site.xml
COPY hdfs-site.xml /opt/hadoop-2.10.1/etc/hadoop/hdfs-site.xml
ENV HADOOP_HOME=/opt/hadoop-2.10.1

RUN rm -rf /opt/apache-hive-2.3.9-bin/metastore_db && /opt/apache-hive-2.3.9-bin/bin/schematool -dbType derby -initSchema

EXPOSE 9083

CMD ["/opt/apache-hive-2.3.9-bin/bin/hive",  "--service", "metastore"]


