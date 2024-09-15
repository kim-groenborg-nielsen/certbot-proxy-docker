
# STAGE 1: Download certbot_proxy
FROM ubuntu:latest AS build
LABEL authors="kgn"
ARG BOT_VERSION=0.1.5
ARG TARGETARCH

WORKDIR /work

RUN apt-get update &&  apt-get install -y curl
RUN curl -v -L30 https://github.com/kim-groenborg-nielsen/certbot_proxy/releases/download/v${BOT_VERSION}/certbot_proxy_${BOT_VERSION}_linux_${TARGETARCH}.tar.gz -o cert-proxy.tgz
RUN echo $(ls -la .)
RUN tar xvzf cert-proxy.tgz


# STAGE 2: build the container to run
FROM gcr.io/distroless/static AS final
LABEL maintainer="kgn"
USER nonroot:nonroot

COPY --from=build --chown=nonroot:nonroot /work/certbot_proxy /certbot_proxy

ENTRYPOINT ["/certbot_proxy"]
