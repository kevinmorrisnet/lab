ARG UBUNTU_VERSION=24.04
FROM ubuntu:${UBUNTU_VERSION}

RUN apt-get update && apt-get install -y curl ca-certificates

WORKDIR /app

COPY greet .

CMD ["./greet"]
