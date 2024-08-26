FROM sinuhedev/base:latest
LABEL maintainer="s@sinuhe.dev"

# install
RUN curl -sSL https://sdk.cloud.google.com | bash
ENV PATH $PATH:/root/google-cloud-sdk/bin

# clean
RUN rm -r /tmp/tmp.*

CMD bash
