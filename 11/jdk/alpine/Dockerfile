FROM alpine:3.12

ARG version=11.0.8.10.1

ADD THIRD-PARTY-LICENSES /
RUN wget -O /etc/apk/keys/amazoncorretto.rsa.pub https://apk.corretto.aws/amazoncorretto.rsa.pub && \
    SHA_SUM="6cfdf08be09f32ca298e2d5bd4a359ee2b275765c09b56d514624bf831eafb91" && \
    echo "${SHA_SUM}  /etc/apk/keys/amazoncorretto.rsa.pub" | sha256sum -c - && \
    echo "https://apk.corretto.aws" >> /etc/apk/repositories && \
    apk add --no-cache amazon-corretto-11=$version-r0

ENV LANG C.UTF-8
ENV JAVA_HOME=/usr/lib/jvm/default-jvm
ENV PATH=$PATH:/usr/lib/jvm/default-jvm/bin
