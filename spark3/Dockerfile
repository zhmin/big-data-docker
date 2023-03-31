FROM openjdk11

WORKDIR /opt
RUN apt-get update && apt-get install -y wget && wget  https://mirrors.tuna.tsinghua.edu.cn/apache/spark/spark-3.3.2/spark-3.3.2-bin-hadoop2.tgz
RUN tar -xzf /opt/spark-3.3.2-bin-hadoop2.tgz

RUN mkdir /opt/hadoop-conf
ENV HADOOP_CONF=/opt/hadoop-conf
COPY core-site.xml /opt/hadoop-conf
COPY hive-site.xml /opt/hadoop-conf

EXPOSE 4040

CMD ["sleep", "infinity"]