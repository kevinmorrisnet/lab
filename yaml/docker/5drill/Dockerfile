FROM busybox:1.35
WORKDIR /opt/app
COPY server.sh /opt/app
RUN chmod +x /opt/app/server.sh
ENV VERSION=2.0
CMD ["sh", "server.sh"]
