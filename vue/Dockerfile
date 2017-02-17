# 基于node环境，生成 vue开发环境镜像
FROM ubuntu/node:latest

MAINTAINER dengchao2056@126.com

RUN  npm install -g vue-cli webpack

RUN mkdir /data

EXPOSE 80 8080 8090

CMD ["/bin/bash"]
