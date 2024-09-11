# docker

[hub.docker.com/u/sinuhedev](https://hub.docker.com/u/sinuhedev)

```bash
# login
docker login

# docker who
docker system info | grep -E 'Username|Registry'
```

## util

```bash
  docker image ls
  docker volume ls
  docker network ls
  docker ps -a

  docker buildx build -t <NAME>:latest .
  docker buildx build -t <NAME>:latest .
  docker exec -it <NAME> bash
  docker run  -it <NAME> bash

  # Stop all containers
  docker kill $(docker ps -aq)

  # Remove all containers
  docker rm $(docker ps -aq)

  # Remove all docker images
  docker rmi $(docker images -q)

  # Remove all docker volumes
  docker volume rm $(docker volume ls -q)

  # PRUNE
  docker system prune
  docker system prune --all

```

## version / tag

```bash
# version
docker buildx build -t "sinuhedev/aws:vX.X.XX" aws

# tag
docker tag my_image sinuhedev/aws:vX.X.XX

```

## base

```bash
docker buildx build -t "sinuhedev/base:latest" base/
docker push sinuhedev/base
#
docker run -it sinuhedev/base
```

## aws

```bash
docker buildx build -t "sinuhedev/aws:latest" aws/
docker push sinuhedev/aws
#
docker run -it sinuhedev/aws
```

## gcp

```bash
docker buildx build -t "sinuhedev/gcp:latest" gcp/
docker push sinuhedev/gcp
#
docker run -it sinuhedev/gcp
```

## s3rver

```bash
docker buildx build -t "sinuhedev/s3rver:latest" s3rver/
docker push sinuhedev/s3rver
#
mkdir .docker/s3/cdn
docker run -p 4568:4568 -v $PWD/.docker/s3:/s3  sinuhedev/s3rver

# test
aws --profile s3rver s3 mb s3://bucket --endpoint-url "http://localhost:4568"
aws --profile s3rver s3 mv file  s3://bucket --endpoint-url "http://localhost:4568"
```

```bash
# S3 public
v .docker/s3/cdn/._S3rver_cors.xml
```

```xml
<CORSConfiguration>
  <CORSRule>
    <AllowedOrigin>*</AllowedOrigin>
    <AllowedMethod>GET</AllowedMethod>
  </CORSRule>
</CORSConfiguration>
```
