# Docker GPU Test

This is a simple repository for running a test against your docker engine to see if it has passthrough access to your CUDA GPU(s).

To double check, you can also run through the steps seen here: https://docs.docker.com/config/containers/resource_constraints/#gpu

## Run the Test

```bash
docker build -t gpu-test .
docker run gpu-test
```

## Remove the Test

```bash
docker ps -a # grab the container ID with the tag "gpu-test"
docker remove <CONTAINER_ID> # use "docker kill <CONTAINER_ID>" as necessary
docker system prune -a -f && docker volume prune -f # OPTIONAL (removes unused containers, images, and volumes)
```