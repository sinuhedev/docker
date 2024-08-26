FROM alpine:3.16.2
LABEL maintainer="s@sinuhe.dev"

RUN apk update
RUN apk add htop

ADD htoprc /root/.config/htop/

CMD htop