FROM node

USER root

WORKDIR /data

# node-sass 注意版本号
# 三种方式，镜像内下载
# RUN wget https://github.com/sass/node-sass/releases/download/v4.9.0/win32-x64-46_binding.node

# 先下载好然后复制到镜像内
COPY ./image /data

RUN set SASS_BINARY_PATH=/data/win32-x64-46_binding.node

# 设置从淘宝源下载
# RUN yarn config set sass_binary_site=https://npm.taobao.org/mirrors/node-sass/ -g

RUN yarn config set registry https://registry.npm.taobao.org



# 由于没有服务，需要让容器不退出
CMD exec /bin/sh -c "trap : TERM INT; (while true; do sleep 1000; done) & wait"
