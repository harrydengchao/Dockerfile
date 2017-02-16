
# 这是一个基于node开发的基础镜像，主要是在这里布置好node环境
# node 版本管理器 n -- https://github.com/tj/n
# node 版本管理器 tnvm -- https://github.com/aliyun-node/tnvm

FROM ubuntu:16.04
# build to ubuntu/node:latest

MAINTAINER dengchao2056@126.com

RUN sed -i 's/archive.ubuntu.com/mirrors.ustc.edu.cn/g' /etc/apt/sources.list && \
    apt-get update

RUN apt-get install -y wget git npm

RUN rm /bin/sh && ln -s /bin/bash /bin/sh

# 安装node包管理器 n，用于获取 node LTS版本、stable版本
RUN npm install -g n

# 安装node包管理器 tnvm，加速下载
# 所有的 npm 操作都需要先执行 . "$HOME/.tnvm/tnvm.sh"，使 tnvm 生效
RUN wget --no-check-certificate -O- https://raw.githubusercontent.com/aliyun-node/tnvm/master/install.sh | bash && \
    export METHOD=script && \
    . "$HOME/.tnvm/tnvm.sh" && \
    tnvm install "node-v$(n --lts)" && \
    tnvm install "node-v$(n --stable)" && \
    tnvm use "node-v$(n --lts)"

EXPOSE 80 8080 8090

CMD ["/bin/bash"]
