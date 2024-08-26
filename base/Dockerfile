FROM alpine:3.16.2
LABEL maintainer="s@sinuhe.dev"

# install
RUN apk update
RUN apk add bash curl git openssh

# localtime
RUN apk add tzdata
RUN cp /usr/share/zoneinfo/Mexico/General /etc/localtime

# nodejs
RUN apk add nodejs npm

# python
RUN apk add python3 py3-pip
RUN ln -s /usr/bin/python3 /usr/bin/python

# clean
RUN apk del tzdata
RUN rm -r /var/cache/apk

CMD bash

