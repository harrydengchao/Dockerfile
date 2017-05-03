# 这是一个基于node开发的基础镜像，主要是在这里布置好node环境
# node 版本管理器 n -- https://github.com/tj/n

FROM ubuntu:16.04
# build to ubuntu/node:latest

MAINTAINER dengchao2056@126.com

RUN sed -i 's/archive.ubuntu.com/mirrors.aliyun.com/g' /etc/apt/sources.list && \
    apt-get update

RUN apt-get install -y wget git npm inetutils-ping net-tools zip

# 安装node包管理器 n，用于获取 node LTS版本、stable版本
RUN npm install -g n && n lts

# 制造一个使用淘宝源的npm 
RUN echo alias tnpm='npm --registry=https://registry.npm.taobao.org' >> ~/.bashrc && source ~/.bashrc

EXPOSE 80 8080 27017

CMD ["/bin/bash"]
