ARG JAVA_VERSION
ARG HADOOP_VERSION
FROM ghcr.io/perara-docker/hadoop/base:$HADOOP_VERSION-java$JAVA_VERSION

MAINTAINER Per-Arne Andersen <per.andersen@uia.no>

HEALTHCHECK CMD curl -f http://localhost:9870/ || exit 1

ENV HDFS_CONF_dfs_namenode_name_dir=file:///hadoop/dfs/name
RUN mkdir -p /hadoop/dfs/name
VOLUME /hadoop/dfs/name

ADD run.sh /run.sh
RUN chmod a+x /run.sh

EXPOSE 9870

CMD ["/run.sh"]
