[![Build Image](https://github.com/hascal/hascal-docker/actions/workflows/publish.yaml/badge.svg)](https://github.com/hascal/hascal-docker/actions/workflows/publish.yaml)

# hascal-docker

Your can use this image to compile and run hascal codes.

For now we only support Arch linux. We are planning to support other OSs in the future.

## basic usage

```dockerfile
FROM hascal/hascal:latest

RUN git clone https://github.com/hascal/hascal.git /hascal

RUN hascal run /hascal/examples/hello.has
```
