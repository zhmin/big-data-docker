FROM openjdk11

WORKDIR /opt
RUN apt-get update && apt-get install -y wget && wget  https://archive.apache.org/dist/hadoop/common/hadoop-2.7.4/hadoop-2.7.4.tar.gz
RUN tar -xzf /opt/hadoop-2.7.4.tar.gz

ENV HADOOP_HOME=/opt/hadoop-2.7.4/
COPY core-site.xml /opt/hadoop-2.7.4/etc/hadoop/core-site.xml
COPY hdfs-site.xml /opt/hadoop-2.7.4/etc/hadoop/hdfs-site.xml

EXPOSE 50075 50020

CMD ["sh", "-c", "$HADOOP_HOME/bin/hdfs datanode"]