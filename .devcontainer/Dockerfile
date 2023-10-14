FROM golang:1.21-bullseye

RUN apt-get update && \
    apt-get install -y protobuf-compiler

RUN useradd -ms /bin/bash vanio

WORKDIR /app

CMD tail -f /dev/null