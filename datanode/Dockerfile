ARG JAVA_VERSION
ARG HADOOP_VERSION
FROM ghcr.io/perara-docker/hadoop/base:$HADOOP_VERSION-java$JAVA_VERSION

MAINTAINER Per-Arne Andersen <per.andersen@uia.no>

HEALTHCHECK CMD curl -f http://localhost:9864/ || exit 1

ENV HDFS_CONF_dfs_datanode_data_dir=file:///hadoop/dfs/data
RUN mkdir -p /hadoop/dfs/data
VOLUME /hadoop/dfs/data

ADD run.sh /run.sh
RUN chmod a+x /run.sh

EXPOSE 9864

CMD ["/run.sh"]
