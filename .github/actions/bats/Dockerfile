FROM ubuntu:latest

ENV LANG en_US.UTF-8
ENV LANGUAGE en_US

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && \
    apt-get install -y --no-install-recommends locales && \
    locale-gen $LANG && \
    apt-get full-upgrade -y && \
    apt-get install -y --no-install-recommends \
        iproute2 \
        qrencode \
        bash \
        bats \
        ca-certificates \
        wget && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]
