# docker

[hub.docker.com/u/sinuhedev](https://hub.docker.com/u/sinuhedev)

```bash
# login
docker login

# docker who
docker system info | grep -E 'Username|Registry'

# version
docker build -t "sinuhedev/aws:vX.X.XX" aws

# tag
docker tag my_image sinuhedev/aws:vX.X.XX

```

## base

```bash
docker build -t "sinuhedev/base:latest" base/
docker push sinuhedev/base
#
docker run -it sinuhedev/base
```

## aws

```bash
docker build -t "sinuhedev/aws:latest" aws/
docker push sinuhedev/aws
#
docker run -it sinuhedev/aws
```

## gcp

```bash
docker build -t "sinuhedev/gcp:latest" gcp/
docker push sinuhedev/gcp
#
docker run -it sinuhedev/gcp
```

## s3rver

```bash
docker build -t "sinuhedev/s3rver:latest" s3rver/
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

## htop

```bash
docker build -t "sinuhedev/htop:latest" htop/
docker push sinuhedev/htop
#
docker run -it sinuhedev/htop
```

## latex

```bash
docker build -t "sinuhedev/latex:latest" latex/
docker push sinuhedev/latex
#
docker run -v $PWD:/PWD sinuhedev/latex file.pdf
docker run -v $PWD:/PWD sinuhedev/latex clean
```

```bash
apt-get update
apt search htop
apt info htop
apt -y install htop
```
