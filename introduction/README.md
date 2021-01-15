The docker container contains a Dockerfile for a tomcat image.

To create the docker container run:

```
docker build -t tomcat .
```

To check the image created run:

```
docker images
```
You can start the container by running:

```
docker run -p 8080:8080 --name=tomcat tomcat
```

Let's break down this.

**docker run** - Runs a command in a new container.

**-p parameter** - Establishes a connection between container's port(s) to the host. By using port1:port2 you make port1 match with port2. After that, you can use port2 in order to access the service that is opened on port1 inside the container. Thus, the container is now connected with outside environments. Usually applications that use some ports in order to run (like tomcat on port 8080, mySQL on port 3306, Apache on port 80, and so) will be restricted in a container to that specific container, unable to communicate with the host or outside network.

**--name=** - The assigned name for the container. This will be what you reference when you run other docker commands against the container. Here we are naming the container tomcat

**tomcat** - The image the container is based on. In this example, we are specifying running the Tomcat image we just created as a container.

To check running containers:

```
docker ps
```

To check all containers including those not running

```
docker ps -a
```

After you started a container you can stop it by using **docker stop [name]**. You can restart the container by typing **docker start [name]**.

Another important command is docker exec, which lets you run a command inside your Docker running container. Note that this only works in running containers, not stopped ones.
