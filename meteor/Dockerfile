# 基于node环境，生成 meteor开发环境镜像
FROM ubuntu/node:latest

MAINTAINER dengchao2056@126.com

RUN apt-get install -y curl language-pack-en

RUN locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8

RUN curl https://install.meteor.com/ | bash

RUN echo "alias mete='meteor --allow-superuser'" >> /etc/profile
RUN /bin/bash -c 'source /etc/profile'

EXPOSE 80 8080 8090 3000

CMD ["/bin/bash"]
