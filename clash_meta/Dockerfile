FROM alpine:3.18.5

EXPOSE 7890/tcp 7891/tcp 9090/tcp

WORKDIR /clash

COPY clash-meta geoip.metadb ./

COPY entrypoint.sh /entrypoint.sh

RUN chmod +x /entrypoint.sh

ENTRYPOINT ["sh","/entrypoint.sh"]