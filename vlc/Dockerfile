ARG BUILD_FROM
FROM ${BUILD_FROM}

# Install VLC
WORKDIR /usr/src
RUN \
    set -x \
    && apk add --no-cache \
        inotify-tools \
        nginx \
        pwgen \
        vlc13 \
    && sed -i 's/geteuid/getppid/' /usr/bin/vlc13 \
    && sed -i '197s#.*#    dir = dir == undefined ? "file:///media" : dir;#' /usr/share/vlc13/lua/http/js/controllers.js
        
WORKDIR /
COPY rootfs /
