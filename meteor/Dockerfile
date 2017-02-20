# 基于node环境，生成 meteor开发环境镜像
FROM ubuntu/node:latest

MAINTAINER dengchao2056@126.com

RUN apt-get install -y curl
RUN  curl https://install.meteor.com/ | sh

RUN mkdir /data

EXPOSE 80 8080 8090

CMD ["/bin/bash"]
