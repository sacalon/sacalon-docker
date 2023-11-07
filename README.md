[![Build Image](https://github.com/sacalon-lang/sacalon-docker/actions/workflows/publish.yaml/badge.svg)](https://github.com/sacalon-lang/sacalon-docker/actions/workflows/publish.yaml)

# Sacalon for Docker

Your can use this image to compile and run sacalon codes.

~For now we only support Arch linux. We are planning to support other OSs in the future.~

## basic usage

```dockerfile
FROM sacalon-lang/sacalon:latest

RUN git clone https://github.com/sacalon-lang/sacalon.git /sacalon  # clone sacalon repo to /sacalon

RUN sacalon run /sacalon/examples/hello.sa  # compile an example code and run it
```
