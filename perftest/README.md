# Perftest example container

This folder contains Dockerfiles which are used to create a basic container
with both `rdma-core` and `perftest` packages installed.

`Dockerfile`: basic image based on `ubuntu:18.04` with `rdma-core` and `perftest` packages compiled and
installed from sources

`Dockerfile.with-cuda` : basic image based on `ubuntu:20.04` with cuda libraries, `rdma-core` and `perftest`
packages compiled and installed from sources.
`perftest` is compiled with cuda support to support GPU-Direct. To successfully run this container, it is required
to run on a host with both RDMA supporing NIC and Nvidia GPU with NVIDIA container runtime installed on the host.

## Buid args

`D_RDMA_CORE_TAG`: linux-rdma/rdma-core tag to use

`D_PERFTEST_TAG`: linux-rdma/perftest tag to use

`D_CUDA_IMAGE`: cuda base image to use (usually taken from https://hub.docker.com/r/nvidia/cuda)

## Build Examples

- `docker build -t perftest-image -f ./Dockerfile ./`
- `docker build --build-arg D_RDMA_CORE_ATH=v31.0 --build-arg D_PERFTEST_TAG=4.4-0.29 -t perftest-image -f ./Dockerfile ./`
- `docker build -t cuda-perftest-image -f ./Dockerfile.use-cuda ./`
- `docker build --build-arg D_RDMA_CORE_TAG=v31.0 --build-arg D_PERFTEST_TAG=4.4-0.29 --build-arg D_CUDA_IMAGE=nvidia/cuda:11.2.1-devel-ubuntu20.04 -t cuda-perftest-image -f ./Dockerfile.use-cuda ./`
- `docker build --build-arg D_RDMA_CORE_TAG=v38.0 --build-arg D_PERFTEST_TAG=v4.5-0.12 --build-arg D_CUDA_IMAGE=nvidia/cuda:11.4.2-devel-ubuntu20.04 -t cuda-perftest-image -f ./Dockerfile.use-cuda ./`

> __Note__: You should use a compatible version of rdma-core, perftest, cuda base image when building the container image
