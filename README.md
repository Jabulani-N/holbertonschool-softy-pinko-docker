# holbertonschool-softy-pinko-docker
Repository demonstrating Docker images

Docker installation:
* [Windows](https://docs.docker.com/desktop/install/windows-install/)

---

Docker is a platform that allows you to containerize your applications, meaning that you can package them into portable, self-contained environments which can run anywhere. This means that you can quickly move your application from one environment to another, such as from your local computer to a server, without worrying about dependencies or configuration issues. Docker achieves this by using containers, which are isolated environments that contain everything an application needs to run, such as libraries, dependencies, and configurations. Docker containers are lightweight and can be started and stopped quickly, making them ideal for modern software development and deployment. With Docker, you can also quickly scale your application by running multiple containers of the same application on different hosts (or the same host, as we will do in this project), and manage them using Docker Compose or other orchestration tools.

Ultimately, what you will create in this project is an infrastructure for an application that utilizes a reverse proxy, a load balancer, two application servers, and one front-end server.

---

### [Docker Overview](https://docs.docker.com/get-started/)

It looks like `apt-get` is the name of the installer. it *seems* to work similar to sudo.
* By that, I mean if you would use `sudo install`, you instead use `apt-get install`.

for setup items used for container creation, preface the command with `RUN`

for repeated action items triggered each time the container is accessed(?), preface with `CMD`

* copying is prefaced by `COPY`, so there is more depth than simply `CMD`.




## Task0
To create a Docker image, you will need to utilize a Dockerfile. Create a Dockerfile that:

* Is based on the latest ubuntu
* Update APT using apt-get update
* Upgrade currently installed software through APT using apt-get upgrade -y
* Once built, you can run the Docker image in a container and it will echo “Hello, World!” on the terminal.

**testing**

`docker build -f ./Dockerfile -t softy-pinko:task0 .;docker run -it --rm --name softy-pinko-task0 softy-pinko:task0` should output one or more lines, ending with 'Hello, World!'

After the first time doing that, just `docker run -it --rm --name softy-pinko-task0 softy-pinko:task0` is fine, as the Hello World is the part you are intereted in seeing

## Task1

For this task, start by making a copy of your task0 directory and name it task1. Next, we want to change the Dockerfile to install Python3, pip3, and Flask. You may not have used Flask, yet, but not to worry; for this project, we will give you all of the Flask code you need to get started. We’ll validate that all have been installed correctly by running a Flask server with one endpoint that when called returns “Hello, World!”

* Install python3, python3-pip, and flask
* * Note: Make sure to automatically install and skip user input with the “-y” flag for apt-get
* * Note: flask must be installed with pip3, not through apt-get
* Locally, create a Python file named api.py and paste the following Python script - it uses Flask to create one endpoint that returns “Hello, World!” when called
* * Hosting this Flask app on 0.0.0.0 instead of 127.0.0.1 means that it is reachable outside of the current machine (the current machine being a Docker container which is running inside of your laptop/desktop)
* * Host this Flask app on port 5252

**testing**

`docker build -f ./Dockerfile -t softy-pinko:task1 .;docker run -p 5252:5252 -it --rm --name softy-pinko-task1 softy-pinko:task1`
