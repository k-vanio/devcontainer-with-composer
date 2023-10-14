FROM golang:1.21-bullseye as builder

RUN apt-get update && \
    apt-get install -y protobuf-compiler

RUN useradd -ms /bin/bash vanio

WORKDIR /app

COPY . .

RUN make install
#RUN make protoc
#RUN make tidy
RUN CGO_ENABLED=0 GOOS=linux go build -o main cmd/main.go
RUN ls -laF

FROM scratch

WORKDIR /app

COPY --from=builder /app/main ./main

EXPOSE 3000

CMD [ "./main" ]