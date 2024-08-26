FROM sinuhedev/base:latest
LABEL maintainer="s@sinuhe.dev"

ENV GLIBC_VERSION 2.34-r0

# glibc
RUN curl -Lo /etc/apk/keys/sgerrand.rsa.pub https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub
RUN curl -Lo glibc.apk "https://github.com/sgerrand/alpine-pkg-glibc/releases/download/${GLIBC_VERSION}/glibc-${GLIBC_VERSION}.apk"
RUN curl -Lo glibc-bin.apk "https://github.com/sgerrand/alpine-pkg-glibc/releases/download/${GLIBC_VERSION}/glibc-bin-${GLIBC_VERSION}.apk"
RUN apk add glibc-bin.apk glibc.apk

# awscli
RUN curl https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip -o awscli.zip
RUN unzip awscli.zip
RUN ./aws/install

# aws-sam-cli
RUN wget https://github.com/aws/aws-sam-cli/releases/latest/download/aws-sam-cli-linux-x86_64.zip -O aws-sam-cli.zip
RUN unzip -qq aws-sam-cli.zip -d aws-sam-cli
RUN aws-sam-cli/install

# clean
RUN rm -r awscli.zip aws
RUN rm -r aws-sam-cli.zip aws-sam-cli
RUN rm -r glibc.apk glibc-bin.apk /etc/apk/keys/sgerrand.rsa.pub

CMD bash
