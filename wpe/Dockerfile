FROM petrosagg/resin-wpe:raspberrypi3-30c7465
ENV WPE_URL="http://localhost:8080"

COPY udev-rules/ /etc/udev/rules.d/

COPY wpe-init /wpe-init

RUN chmod +x wpe-init

CMD [ "/wpe-init" ]
