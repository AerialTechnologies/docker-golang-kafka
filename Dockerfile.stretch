FROM golang:1.13-stretch

ENV LZ4_VERSION=1.9.1 \
    LIBRDKAFKA_VERSION=1.1.0

RUN apt-get update && apt-get dist-upgrade -y && \
    apt-get install -y bash zlib1g-dev libffi-dev build-essential make git ssh && \
    curl -Ls https://github.com/lz4/lz4/archive/v${LZ4_VERSION}.tar.gz | tar -xz -C /tmp && \
    cd /tmp/lz4-${LZ4_VERSION} && make && make install && rm -fr /tmp/lz4-${LZ4_VERSION} && \
    curl -Ls https://github.com/edenhill/librdkafka/archive/v${LIBRDKAFKA_VERSION}.tar.gz | tar -xz -C /tmp && \
    cd /tmp/librdkafka-${LIBRDKAFKA_VERSION} && ./configure && make && make install && rm -fr /tmp/librdkafka-${LIBRDKAFKA_VERSION} && \
    ldconfig

WORKDIR /root

CMD []
