FROM openjdk11

WORKDIR /opt
RUN apt-get update && apt-get install -y wget && wget https://mirrors.tuna.tsinghua.edu.cn/apache/hadoop/common/hadoop-2.10.1/hadoop-2.10.1.tar.gz
RUN tar -xzf /opt/hadoop-2.10.1.tar.gz

ENV HADOOP_HOME=/opt/hadoop-2.10.1/
COPY core-site.xml /opt/hadoop-2.10.1/etc/hadoop/core-site.xml
COPY hdfs-site.xml /opt/hadoop-2.10.1/etc/hadoop/hdfs-site.xml

RUN $HADOOP_HOME/bin/hdfs namenode -format -force

EXPOSE 50070

CMD ["sh", "-c", "$HADOOP_HOME/bin/hdfs namenode"]