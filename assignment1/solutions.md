After installing all the .deb packages on the machine
chekck if `docker` has been installed successfully
```console
systemctl status docker
```
**Problem1**
- run the container hello-world
```shell
docker run hello
```
- create a container from that image
```shell
docker container run -it --name my-first-container hello-world
```
- check the container status
```shell
docker container ls -a
```
- start the stopeed container
```shell
docker container start my-first-container
```
- remove the container
```shell
docker container rm my-first-container
```
- remove the image
```shell
docker container rm hello-world
```

**Problem2**
- first, i pulled the `nodejs` image from the dockerhub registery
```shell
docker pull node
```
- create a container instance from the `node` image
```shell
docker container run -t -d --name first-node-app node
``` 
- Get into the container
```shell
docker container exec -it first-node-app bash
```
- then run the following command
```shell
echo docker
```
- touch a file
```shell
touch hello-docker
```
- stop the container first
```shell
docker container stop first-node-app
```
- then remove it
```shell
docker container remove first-node-app
```
- to remove all stopeed contaiers
```shell
docker container stop $(docker contaier ls -q)
```
>:bulb: the `-q` option to return just the container id


