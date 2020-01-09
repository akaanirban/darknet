![Darknet Logo](http://pjreddie.com/media/files/darknet-black-small.png)

# Darknet #
Darknet is an open source neural network framework written in C and CUDA. It is fast, easy to install, and supports CPU and GPU computation.

For more information see the [Darknet project website](http://pjreddie.com/darknet).

For questions or issues please use the [Google Group](https://groups.google.com/forum/#!forum/darknet).


## To build locally:
```bash 
git clone https://github.com/akaanirban/darknet.git
cd darknet
make
```
### To build a docker image on Alpine Linux check [this link](https://hub.docker.com/r/jcjimenez/darknet-docker/dockerfile).
```docker
FROM alpine:3.7

RUN apk add --update --no-cache \
    alpine-sdk

# Install darknet
RUN git clone https://github.com/akaanirban/darknet.git /darknet
WORKDIR /darknet
RUN echo '#include <sys/select.h>' > examples/go.c.updated
RUN cat examples/go.c >> examples/go.c.updated
RUN mv examples/go.c.updated examples/go.c
RUN make
```
