# Firefox over VNC

This sample is copy from <https://docs.docker.com/engin/reference/builder/>

After you copy the file, you can use `docker build -t <aliasname>` to build
this image.

After build image, you can use `docker run -p 5900:5900 <aliasname>` to run
the container.

After container is up, use `vncviewer <container-ip>` to enter container over VNC

 
