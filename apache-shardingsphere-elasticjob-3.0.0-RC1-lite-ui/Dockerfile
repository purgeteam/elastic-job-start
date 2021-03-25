FROM registry.cn-shanghai.aliyuncs.com/purgeteam-jdk/openjdk:8-jdk-alpine
MAINTAINER pader "purgeteam"

ENV BASE_DIR="/home/elastic-job"

WORKDIR /$BASE_DIR

ADD bin/start.sh bin/start.sh
ADD conf/application.properties conf/application.properties
ADD lib/ lib/
ADD ext-lib/ ext-lib/

RUN echo "Asia/Shanghai" >/etc/timezone
RUN sh -c 'touch /application.jar'

ENV JAVA_OPTS=""

CMD exec sh bin/start.sh
EXPOSE 8088