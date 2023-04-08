FROM nginx:1.13.9-alpine

LABEL maintainer="yueyazhui <15235032479@163.com>"

ARG TZ='Asia/Shanghai'

ENV TZ ${TZ}

RUN apk upgrade --update \
    && apk add bash git \
    && rm -rf /usr/share/nginx/html \
    && git clone https://github.com/yueyazhui/blog.git /usr/share/nginx/html \
    && ln -sf /usr/share/zoneinfo/${TZ} /etc/localtime \
    && echo ${TZ} > /etc/timezone \
    && rm -rf /var/cache/apk/*

# ADD entrypoint.sh /entrypoint.sh #容易报错
# ADD flush /usr/local/bin/flush #容易报错

WORKDIR /usr/share/nginx/html

# CMD ["/entrypoint.sh"] #容易报错
