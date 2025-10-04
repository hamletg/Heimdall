FROM nginx:alpine
RUN apk add util-linux openrc
VOLUME /sys/fs/cgroup
RUN echo http://dl-2.alpinelinux.org/alpine/edge/community/ >> /etc/apk/repositories\
    && apk add -U tailscale\
    && mkdir /run/openrc\
    && touch /run/openrc/softlevel      # Workaround for the Error Message
    && rc-update add tailscale
  
COPY ./default.conf /etc/nginx/conf.d