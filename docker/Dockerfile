FROM --platform=$TARGETOS/$TARGETARCH amazoncorretto:21-al2023

LABEL author="Your Name" maintainer="oscar@stougaard.com"
LABEL org.opencontainers.image.source="https://github.com/AbdisKiosk/docker-images"
LABEL org.opencontainers.image.licenses=MIT

RUN yum update -y \
    && yum install -y lsof curl ca-certificates openssl git tar sqlite shadow-utils fontconfig freetype tzdata iproute libstdc++ \
    && useradd -d /home/container -m container \
    && yum clean all

USER container
ENV USER=container HOME=/home/container
WORKDIR /home/container

COPY ./entrypoint.sh /entrypoint.sh
CMD [ "/bin/bash", "/entrypoint.sh" ]
