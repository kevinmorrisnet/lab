FROM alpine:3.18
WORKDIR /app
COPY run.sh .
RUN chmod +x /app/run.sh
ENV APP_ENV=production
EXPOSE 8080
CMD ["sh", "run.sh"]



