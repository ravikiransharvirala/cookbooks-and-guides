# Docker

### What is Docker?
Docker is a tool designed to make it easier to create, deploy, and run application by using containers

### What does Container mean?
Containers allow developer to package up an application with all parts it needs sucb as libraries and other dependencies and ship it all out as one package

### Containers vs Virtual Machines
 - Containers are abstraction at the app layer that packages code and dependencies together
 - Virtual Machines(VM) are an abstraction of physical hardware turining one server into many servers

 *source: docker.com*

 ### Docker Flow

**Dockerfile** -> **Images** -> **Container**

### Running things Docker
- Container have main process
- The container stops when that process stops
- Containers have names

### Container Networking ###
- Programs in the container are isolated from internet by default
- You can group containers into 'private' networks
- You can explicitly choose who can connect to whom
- Expose ports to let connections in
- Private networks to connect between containers

### Images
 - You can download existing images from hub.docker.com or
 - You can create your own image from docker file
 - Always tag images in this format **Organization/image-name**

### Volumes
- You can create volumes in containers
- Volumes are virtual discs to store and share data 
- There are two main varieties of volumes
    - **Persistent** - will be available on the host even when the container goes awsy
    - **Ephemeral** - will be gone once the conatiner goes away
- They are not part of the image

### Dockerfile
 - It is a small program to create an image
 - Each line takes the image from the previous line and make another image
 - The previous image is unchanged

 ### Dockerfile Instruction syntax
 - `**FROM**` to start with an base image
 - `**RUN**` to run a command in the container
 - `**CMD**` to run a command when this image is started
 - `**LABEL**` to add metadata to an image
 - `**EXPOSE**` to actually publish the port when running the container
 - `**ENV**` to set env variables while running the container
 - `**ADD**` to copy new files, directories and remove file url's from `<src>` and adds them to the filesystem of image at path `<dest>`

### Docker key commands and tags

- To get images from the docker hub

```bash
$ docker pull <ORGANIZATION/image-name> or <image-name>
```

- To get list of images

```bash
$ docker images
REPOSITORY         TAG         IMAGE ID       CREATED        SIZE
```

- To build a image from docker file. Run the below command from the directory that contains docker file

```bash
$ docker build -t <Give your new image a name> . 
```
*Note: There is a dot at the end of the command* 

- To convert the image to running container

```bash
$ docker run -ti <image name>:<image tage>
```


**Options**
- `-ti` - for initiating the interactive terminal upon running the images
- `--rm` - deletes the container when the process finishes running
- `-d` - detach from the container (mainly used if you want to keep the container running in the background)
- `-name` - to name the container
- `-p` - publish a container port (Example: -p <port from local:container port>)
- `-v` - to mount a volume to the container (Example: -v <folder path of the host: shared folder from the container > )

**Resource Constraints**
- `--memory` - To specify the memory limits for a container
- `--cpu-shares` - To specify the cpu shares relative to other containers
- `--cpu-quota` - To limit in general
- `--volumes-from` - To share the volume from different container


- To check active containers (running containers)

```bash
$ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
```
`-a` - to list all the containers
`-l` - recently stopped containers

- To convert a container to an image

```bash
$ docker commit <CONTAINER ID> <give a name to your new image:tag(optional)>
```
or
```bash
$ docker commit <NAMES:container name> <give a name to your new image:tag(optional)>
```

- To attach to the existing container

```bash
$ docker attach <CONTAINER ID> or <CONTAINER NAMES>
```

- ctrl+p and ctrl+q to dettach from the container

- To start another process in an existing container

```bash
$ docker exec
```

- To look at logs of a container

```bash
$ docker logs <CONTAINER NAME>
```

- To stop a running container

```bash
$ docker kill <CONTAINER NAME>
```

- To remove a container

```bash
$ docker rm <CONTAINER NAME>
```

- To remove a image

```bash
$ docker rmi <IMAGE NAME>
```