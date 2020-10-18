# mlnx-dockerfiles

## How to use this Docker image

```sh
$ git clone https://github.com/moshe010/mlnx-dockerfiles.git
$ cd mlnx-dockerfiles
$ docker build -f <Dockerfile> -t <tag> .
```

## How to use this Docker image for spacific OFED version
```sh
$ docker build --build-args VERSION=<ofed version>  -f <Dockerfile> -t <tag> .
```
