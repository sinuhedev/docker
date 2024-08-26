FROM sinuhedev/base:latest

# install
RUN npm i -g s3rver

WORKDIR /s3
EXPOSE 4568

CMD s3rver -a 0.0.0.0 -p 4568 -d /s3
