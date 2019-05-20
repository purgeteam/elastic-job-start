# elastic-job-docker

[![Build Status](https://secure.travis-ci.org/elasticjob/elastic-job-lite.png?branch=master)](https://travis-ci.org/elasticjob/elastic-job-lite)
[![Maven Status](https://maven-badges.herokuapp.com/maven-central/com.dangdang/elastic-job-lite/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.dangdang/elastic-job-lite)
[![Gitter](https://badges.gitter.im/Elastic-JOB/elastic-job-lite.svg)](https://gitter.im/Elastic-JOB/elasticjob?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)
[![Coverage Status](https://coveralls.io/repos/elasticjob/elastic-job/badge.svg?branch=master&service=github)](https://coveralls.io/github/elasticjob/elastic-job?branch=master)
[![GitHub release](https://img.shields.io/github/release/elasticjob/elastic-job.svg)](https://github.com/elasticjob/elastic-job/releases)
[![License](https://img.shields.io/badge/license-Apache%202-4EB1BA.svg)](https://www.apache.org/licenses/LICENSE-2.0.html)

Elastic-Job console封装为docker版本.

### 下载
docker images 地址：
```text
docker pull registry.cn-hangzhou.aliyuncs.com/engine/elastic-job-lite-console:latest
```

### 启动命令
克隆本工程
```text
cd [本文件]/example

docker-compose -f elastic-job-lite-console.yaml up
```
或者docker run方式
```text
docker run -d --name elastic-job-lite-console -p 8899:8899 registry.cn-hangzhou.aliyuncs.com/engine/elastic-job-lite-console:latest
```

### 访问

```text
http://127.0.0.1:8899
```
```text
默认管理密码root/root
默认访客密码guest/guest
```
