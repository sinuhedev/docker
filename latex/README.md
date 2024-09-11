# latex

```bash
docker buildx build -t "sinuhedev/latex:latest" latex/
docker push sinuhedev/latex
#
docker run -v $PWD:/PWD sinuhedev/latex file.pdf
docker run -v $PWD:/PWD sinuhedev/latex clean
```
