# an example to build a tiny docker image

## Pin a specific OS version
選定好特定的版本的 OS，如 Ubuntu 16.04
因為此方法做出來的 docker image 可能只能用在特定的版本、特定的 OS

## Pin a specific version

## Use ldd to investigate required .so file 

**ldd** prints the shared objects (shared libraries) required by each program or shared object specified on the command line.

e.g.
```
ldd /bin/ping
``` 

## write dockerfile and copy share objects to the same directory.

```
FROM scratch                                                                                                                              
MAINTAINER Jeff Chan <pm751211@gmail.com>

COPY libcap.so.2 /lib/x86_64-linux-gnu/libcap.so.2
COPY libc.so.6 /lib/x86_64-linux-gnu/libc.so.6
COPY ld-linux-x86-64.so.2 /lib64/ld-linux-x86-64.so.2
COPY ping /bin/ping

```

## build docker image

```
docker build -t ping .
```

## Use it !

```
docker run --rm ping ping -c 10 8.8.8.8
```
