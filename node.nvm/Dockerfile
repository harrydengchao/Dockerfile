# 这是一个基于node开发的基础镜像，主要是在这里布置好node环境
# node 版本管理器 nvm -- https://github.com/creationix/nvm

FROM ubuntu:16.04

MAINTAINER dengchao2056@126.com

RUN sed -i 's/archive.ubuntu.com/mirrors.aliyun.com/g' /etc/apt/sources.list && \
    apt-get update

RUN apt-get install -y wget git inetutils-ping net-tools zip

# 安装node包管理器 nvm，用于获取 node LTS版本
RUN wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.33.2/install.sh | bash

RUN export NVM_DIR="$HOME/.nvm" && \
    [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" && \
    [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion" && \
    # 改源为 淘宝nvm源
    export NVM_NODEJS_ORG_MIRROR=http://npm.taobao.org/mirrors/node && \
    nvm install --lts

# 淘宝nvm源 写入变量
RUN echo 'NVM_NODEJS_ORG_MIRROR=http://npm.taobao.org/mirrors/node' >> ~/.bashrc && /bin/bash -c "source ~/.bashrc"

# 制造一个使用淘宝源的 tnpm 
RUN echo alias tnpm="'npm --registry=https://registry.npm.taobao.org'" >> ~/.bashrc && /bin/bash -c "source ~/.bashrc"

EXPOSE 80 8080 27017 3306

CMD ["/bin/bash"]
