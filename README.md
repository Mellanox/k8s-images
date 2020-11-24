# k8s-images

## How to use this Docker image

```sh
$ git clone https://github.com/Mellanox/k8s-images.git
$ cd k8s-images
$ docker build -f <Dockerfile> -t <tag> .
```

## How to use this Docker image for spacific OFED version
```sh
$ docker build --build-args VERSION=<ofed version>  -f <Dockerfile> -t <tag> .
```
