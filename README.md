# alpine-ssh

A minimal Docker image based on Alpine Linux with a complete package index and only 5 MB in size!

# How to build this Dockerfile.

```
$ docker build --build-arg \
    PASSWORD=toor \
    -t containerpi/alpine-sshd:latest \
    -f Dockerfile .
```

# How to run the docker container with ssh ?

I have exposed the port 22 in the Dockerfile. You can use the below command to run&test the docker container.

```
$ sudo docker run -d --name test_sshd \
    -p 2222:22 \
    containerpi/alpine-sshd:latest

$ ssh root@localhost -p 2222
# The password is `toor`

$ sudo docker port test_sshd 22
0.0.0.0:2222
:::2222
```
