# holbertonschool-softy-pinko-docker
Repository demonstrating Docker images

Docker installation:
* [Windows](https://docs.docker.com/desktop/install/windows-install/)

---

Docker is a platform that allows you to containerize your applications, meaning that you can package them into portable, self-contained environments which can run anywhere. This means that you can quickly move your application from one environment to another, such as from your local computer to a server, without worrying about dependencies or configuration issues. Docker achieves this by using containers, which are isolated environments that contain everything an application needs to run, such as libraries, dependencies, and configurations. Docker containers are lightweight and can be started and stopped quickly, making them ideal for modern software development and deployment. With Docker, you can also quickly scale your application by running multiple containers of the same application on different hosts (or the same host, as we will do in this project), and manage them using Docker Compose or other orchestration tools.

Ultimately, what you will create in this project is an infrastructure for an application that utilizes a reverse proxy, a load balancer, two application servers, and one front-end server.

---

[Docker Overview](https://docs.docker.com/get-started/)


## Task0

**testing**

`docker build -f ./Dockerfile -t softy-pinko:task0 .;docker run -it --rm --name softy-pinko-task0 softy-pinko:task0` should output one or more lines, ending with 'Hello, World!'

After the first time doing that, just `docker run -it --rm --name softy-pinko-task0 softy-pinko:task0` is fine, as the Hello World is the part you are intereted in seeing