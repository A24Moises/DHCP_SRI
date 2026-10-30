FROM debian:13
RUN echo 'Acquire::http { Proxy "http://10.0.5.7:8080"; };' >/etc/apt/apt.conf.d/02proxy

RUN apt update  && apt install -y \
    procps \
    iproute2 \
    iputils-ping \
    bind9utils \
    dnsutils \
    tcpdump \
    dhcp-helper \
    nftables \
    && rm -rf /var/lib/apt/lists/*

COPY entrypoint.sh /sbin/entrypoint.sh

RUN chmod 777 /sbin/entrypoint.sh

ENTRYPOINT ["/sbin/entrypoint.sh"]