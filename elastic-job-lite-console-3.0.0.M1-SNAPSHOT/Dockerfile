FROM centos:7.5.1804
MAINTAINER pader "1346735074@qq.com"

# set environment
ENV MODE="cluster" \
#    PREFER_HOST_MODE="ip"\
    BASE_DIR="/home/elastic-job" \
    CLASSPATH=".:/home/elastic-job/conf:$CLASSPATH" \
#    CLUSTER_CONF="/home/elastic-job/conf/cluster.conf" \
    FUNCTION_MODE="all" \
    JAVA_HOME="/usr/lib/jvm/java-1.8.0-openjdk" \
#    NACOS_USER="nacos" \
    JAVA="/usr/lib/jvm/java-1.8.0-openjdk/bin/java" \
    TIME_ZONE="Asia/Shanghai"

ARG ELASTIC_VERSION=3.0.0.M1-SNAPSHOT

WORKDIR /$BASE_DIR

RUN set -x \
    && yum update -y \
    && yum install -y java-1.8.0-openjdk java-1.8.0-openjdk-devel wget iputils nc  vim libcurl\

    # 下载启动包
#    && wget  https://github.com/alibaba/nacos/releases/download/${ELASTIC_VERSION}/nacos-server-${ELASTIC_VERSION}.tar.gz -P /home \
    && wget  https://github.com/purgeteam/elastic-job-start/releases/download/${ELASTIC_VERSION}/elastic-job-lite-console-${ELASTIC_VERSION}.tar.gz -P /home \

    # 解压启动包
#    && tar -xzvf /home/nacos-server-${ELASTIC_VERSION}.tar.gz -C /home \
    && tar -xzvf /home/elastic-job-lite-console-${ELASTIC_VERSION}.tar.gz -C /home \

#    && rm -rf /home/nacos-server-${ELASTIC_VERSION}.tar.gz /home/nacos/bin/* /home/nacos/conf/*.properties /home/nacos/conf/*.example /home/nacos/conf/nacos-mysql.sql \

    && yum autoremove -y wget \
    && ln -snf /usr/share/zoneinfo/$TIME_ZONE /etc/localtime && echo '$TIME_ZONE' > /etc/timezone \
    && yum clean all


#ADD bin/docker-startup.sh bin/docker-startup.sh
ADD bin/start.sh bin/start.sh


#ADD conf/application.properties conf/application.properties
ADD conf/auth.properties conf/auth.properties

#ADD init.d/custom.properties init.d/custom.properties
#ADD lib/activation-1.1.jar lib/activation-1.1.jar
ADD lib/ lib/


# set startup log dir
RUN mkdir -p logs \
	&& cd logs
#	&& touch start.out \
#	&& ln -sf /dev/stdout start.out \
#	&& ln -sf /dev/stderr start.out
RUN chmod +x bin/start.sh

EXPOSE 8899
ENTRYPOINT ["bin/start.sh"]