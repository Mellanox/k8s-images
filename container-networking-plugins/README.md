Container Networking Plugins

Build docker image of [containernetworking-plugins](https://github.com/containernetworking/plugins) with given release and architecture

Building image with default args, `ARCH=amd64` and `VERSION=v0.8.7`
```
$ docker build -t mellanox/containernetworking-plugins .
```

Building with changing ARGS
```
$ docker build --build-arg ARCH=<arch> --build-arg VERSION=<version> -t mellanox/containernetworking-plugins .
```
