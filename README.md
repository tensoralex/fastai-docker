# Dockerfiles for Pytorch Deeplearning environment
### Supports http://fast.ai Part1 v2 course

* Dockerfile8 - CUDA8 environment
* Dockerfile9 - CUDA9 environment

## Prerequisites:
* Docker installed
* For use on GPU - [nvidia-docker](https://github.com/NVIDIA/nvidia-docker) should be installed additionally

## Usage:

### Build:

* docker build -t fastai_docker_cuda8:part1v2 -f Dockerfile8 .

or
* docker build -t fastai_docker_cuda9:part1v2 -f Dockerfile9 .

### Run:

###### Note: To run using GPU you need to have nvidia-docker installed.

* nvidia-docker run --rm -v /path/to/your/data/on/host:/workspace/hostfsmnt -P  --ipc=host -it fastai_docker_cuda8:part1v2


* nvidia-docker run --rm -v /path/to/your/data/on/host:/workspace/hostfsmnt -P  --ipc=host -it fastai_docker_cuda9:part1v2


Ports are intentionally left dynamic to run multiple containers simultaneously.
To find a port:
```sh
$ docker ps
CONTAINER ID        IMAGE                          COMMAND                  CREATED             STATUS              PORTS                     NAMES
304d73008508        fastai_docker_cuda9:part1v2    "/bin/bash /worksp..."   12 seconds ago      Up 11 seconds       0.0.0.0:32780->8888/tcp   peaceful_shockley


```

Default Jupyter password: jupyter
