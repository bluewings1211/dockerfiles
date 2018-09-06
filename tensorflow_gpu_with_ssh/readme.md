# Build Image

Use `docker build -t tf_with_ssh .` to build image

# Use Image

Use `docker run -it -p 8022:22 -p 8888:8888  tf_with_ssh:latest` to run container. You can use `ssh -p 8022 root@localhost` to login to container.


