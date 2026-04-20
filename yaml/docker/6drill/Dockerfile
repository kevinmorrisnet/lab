FROM alpine:3.18
WORKDIR /opt
COPY app.sh /opt
RUN chmod +x /opt/app.sh
ENV APP_ENV=staging
ENV APP_VER=1.0
CMD ["sh", "app.sh"]


