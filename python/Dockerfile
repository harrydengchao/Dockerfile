# 基于Ubuntu的Python开发镜像

FROM ubuntu:16.04

MAINTAINER dengchao2056@126.com

RUN sed -i 's/archive.ubuntu.com/mirrors.ustc.edu.cn/g' /etc/apt/sources.list && \
    apt-get update

RUN apt-get install -y wget git python3 inetutils-ping net-tools

EXPOSE 80 8080 8090 3000

CMD ["/bin/bash"]
