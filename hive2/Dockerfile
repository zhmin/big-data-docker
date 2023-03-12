FROM openjdk11

WORKDIR /opt
# RUN apt-get update && apt-get install -y wget && wget https://mirrors.tuna.tsinghua.edu.cn/apache/hive/hive-2.3.9/apache-hive-2.3.9-bin.tar.gz

COPY  apache-hive-2.3.9-bin.tar.gz /opt
RUN tar -xzf apache-hive-2.3.9-bin.tar.gz
COPY hive-env.sh  apache-hive-2.3.9-bin/conf/
COPY hive-site.xml  apache-hive-2.3.9-bin/conf/

COPY hadoop-2.7.4.tar.gz /opt
RUN tar -xzf hadoop-2.7.4.tar.gz

ENV HADOOP_HOME=/opt/hadoop-2.7.4

RUN rm -rf /opt/apache-hive-2.3.9-bin/metastore_db && /opt/apache-hive-2.3.9-bin/bin/schematool -dbType derby -initSchema

EXPOSE 9083

CMD ["/opt/apache-hive-2.3.9-bin/bin/hive",  "--service", "metastore"]


