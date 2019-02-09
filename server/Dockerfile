FROM balenalib/raspberrypi3-alpine-node

ENV NODE_ENV production

WORKDIR /opt/magic_mirror

# Clone the repo
RUN apk add -U git && \
    git clone --depth 1 https://github.com/MichMich/MagicMirror.git . && \
    apk del git && \
    rm -rf /var/cache/apk/*

# Install dependencies
RUN JOBS=MAX npm install --production --unsafe-perm && \
    npm cache verify && \
    rm -rf /tmp/*

COPY modules/* /opt/magic_mirror/modules/
COPY config/* /opt/magic_mirror/config/
COPY css/* /opt/magic_mirror/css/

EXPOSE 8080
CMD ["node serveronly"]
