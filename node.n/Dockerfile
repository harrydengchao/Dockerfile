# 这是一个基于node开发的基础镜像，主要是在这里布置好node环境
# node 版本管理器 n -- https://github.com/tj/n

FROM ubuntu:16.04
# build to ubuntu/node:latest

MAINTAINER dengchao2056@126.com

RUN sed -i 's/archive.ubuntu.com/mirrors.aliyun.com/g' /etc/apt/sources.list && \
    apt-get update

RUN apt-get install -y wget git inetutils-ping net-tools zip

# 安装node包管理器 n，用于获取 node LTS版本
RUN apt-get update && apt-get install -y npm
RUN npm install -g n
RUN export NODE_MIRROR=http://npm.taobao.org/mirrors/node/  && \
    n lts

# 淘宝node源 写入变量
RUN echo 'export NODE_MIRROR=http://npm.taobao.org/mirrors/node/' >> /etc/bash.bashrc && /bin/bash -c "source /etc/bash.bashrc"

# 制造一个使用淘宝源的 tnpm 
RUN echo alias tnpm="'npm --registry=https://registry.npm.taobao.org'" >> ~/.bashrc && /bin/bash -c "source ~/.bashrc"

EXPOSE 80 8080 27017 3306

CMD ["/bin/bash"]