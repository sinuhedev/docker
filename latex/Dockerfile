FROM debian:11.6-slim

RUN apt-get update
RUN apt -y install texlive-full biber

ADD script /
WORKDIR /PWD

# CMD bash /build
ENTRYPOINT ["/script"]