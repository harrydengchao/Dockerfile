# 基于node环境，生成 weex开发环境镜像
FROM ubuntu/node:latest

MAINTAINER dengchao2056@126.com

# 使用 tnvm时，所有的 npm 操作都需要先执行 . "$HOME/.tnvm/tnvm.sh"，使 tnvm 生效
# RUN . "$HOME/.tnvm/tnvm.sh" && \
#     npm install -g cnpm && \
#     cnpm install -g weex-toolkit@beta

# 使用 n时。可直接使用 npm
RUN  npm install -g cnpm && \
    cnpm install -g weex-toolkit@beta

RUN mkdir /data

EXPOSE 80 8080 8090

CMD ["/bin/bash"]
