# 基于Ubuntu的Python开发镜像

FROM ubuntu:16.04

MAINTAINER dengchao2056@126.com

RUN sed -i 's/archive.ubuntu.com/mirrors.aliyun.com/g' /etc/apt/sources.list && \
    apt-get update

RUN apt-get install -y wget git python3 inetutils-ping net-tools

# 更换 pip 为国内原
RUN mkdir ~/.pip && touch pip.conf && echo [global] >> test.conf && echo index-url = https://pypi.mirrors.ustc.edu.cn/simple >> test.conf

EXPOSE 80 8080 27017 3000

CMD ["/bin/bash"]
