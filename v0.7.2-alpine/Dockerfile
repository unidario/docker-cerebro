FROM openjdk:8-jre-alpine

RUN apk add --no-cache bash

RUN apk update \
    && apk add ca-certificates \
    && update-ca-certificates \
    && apk add openssl

ENV CEREBRO_VERSION 0.7.2

RUN mkdir /opt \
    && cd /opt \
    && wget -O cerebro-${CEREBRO_VERSION}.tgz https://github.com/lmenezes/cerebro/releases/download/v${CEREBRO_VERSION}/cerebro-${CEREBRO_VERSION}.tgz \
    && tar zxvf cerebro-${CEREBRO_VERSION}.tgz \
    && rm cerebro-${CEREBRO_VERSION}.tgz \
    && mkdir cerebro-${CEREBRO_VERSION}/logs \
    && mv cerebro-${CEREBRO_VERSION} cerebro

WORKDIR /opt/cerebro

EXPOSE 9000

CMD ["./bin/cerebro"]
