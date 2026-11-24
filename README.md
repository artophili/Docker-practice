# Docker-practice
Practice codespaces

Docker isolates the application from the rest of the host machine
Docker helps to isolate so the changes made in that container will not affect the host machine at all.

docker run hello-world
first it finds the image locally. If not found it pull from library 
Pull complete message appears
Then it download the image
Then digest and the final status appears where we can see new image downloaded

To generate, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

Docker image - Image does not preserve state. 

docker run -it python:3.13.11-slim
Here python is a docker image name and name:tag they together form a image name

docker run -it --entrypoint=bash python:3.13.11-slim
By this command, we can run the image but the entry point will be bash 

docker ps -a : This command will show all the exisiting images info like container id, Image, command, created, status, ports, names

Volume mapping - 
docker run -it --entrypoint=bash -v $(pwd)/test:/app/test python:3.13.11-slim
The above command will map the host file path to the docker container location using Volume
-v $(pwd)/test:/app/test - Here on the left side of : there is host machine location and on the right side there is docker container location where we have to map the volume

 Data pipeines
 It takes some input and produces some output
Pipeline scripts are often contain parameter. They are for parameterized jobs so that scheduler can run the same same script for different periods without editing code

Isloation virtual environments so that we can install required dependencies in the particular environment only and not on the host machine.
import uv
uv init --python 3.13 : This initiates a python environment
uv run python -V : To run environment

