FROM alpine:latest

RUN set -ex && \
    apk --no-cache add ca-certificates && \
    apk --no-cache add ca-certificates wget && \
    wget -q -O /etc/apk/keys/sgerrand.rsa.pub https://raw.githubusercontent.com/sgerrand/alpine-pkg-glibc/master/sgerrand.rsa.pub && \
    wget https://github.com/sgerrand/alpine-pkg-glibc/releases/download/2.27-r0/glibc-2.27-r0.apk && \
    apk add glibc-2.27-r0.apk && \
    rm glibc-2.27-r0.apk

ENV PATH /etc/goflyway:$PATH

CMD ["go.sh"]
