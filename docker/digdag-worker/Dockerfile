FROM golang:1.15-buster as builder

ENV CGO_ENABLED=0

RUN apt update && apt install -y --no-install-recommends git wget unzip make

WORKDIR /app
RUN wget -q https://github.com/h3poteto/kube-job/archive/refs/tags/v0.5.1.zip \
    && unzip -q v0.5.1.zip
RUN make -C /app/kube-job-0.5.1 build

FROM azul/zulu-openjdk:8

RUN apt-get update -qq && apt-get install -y curl wget unzip

RUN curl -o /usr/local/bin/digdag --create-dirs -L 'https://dl.digdag.io/digdag-0.10.0' \
    && chmod +x /usr/local/bin/digdag

COPY --from=builder /app/kube-job-0.5.1/bin/kube-job /usr/local/bin/
