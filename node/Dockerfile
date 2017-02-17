# 这是一个基于node开发的基础镜像，主要是在这里布置好node环境
# node 版本管理器 n -- https://github.com/tj/n

FROM ubuntu:16.04
# build to ubuntu/node:latest

MAINTAINER dengchao2056@126.com

RUN sed -i 's/archive.ubuntu.com/mirrors.ustc.edu.cn/g' /etc/apt/sources.list && \
    apt-get update

RUN apt-get install -y wget git npm

# 安装node包管理器 n，用于获取 node LTS版本、stable版本
RUN npm install -g n && n lts

EXPOSE 80 8080 8090

CMD ["/bin/bash"]
