# All Dockerfiles need to start from a base Linux image.
# Docker has a hub (http://hub.docker.com) where you can see all Images submitted by users and
# where you can submit your own images. This is like a github for Docker images.
# We will start from java:8-jre. This is an ubuntu machine with java 8 installed on it.
# The keyword here is FROM.
FROM java:8-jre

# The KEYWORD ENV it let us specify some Linux environment variables
# Here we will set CATALINA_HOME (the home of the tomcat server)
ENV CATALINA_HOME /usr/local/tomcat
ENV PATH $CATALINA_HOME/bin:$PATH


# RUN lets you run Linux commands inside the image.
# The \ symbol allows you to continue the command onto the next line
# The && allows you to string multiple commands together. This is preferred over having a RUN statement for each command
# Here we will navigate into /usr/local then download tomcat from the server
# then decompress it and rename it to /tomcat.
# The final path to tomcat will be /usr/local/tomcat.
RUN cd /usr/local/ \
     && wget http://mirrors.m247.ro/apache/tomcat/tomcat-8/v8.5.61/bin/apache-tomcat-8.5.61.tar.gz \
     && tar xzf apache-tomcat-8.5.61.tar.gz \
     && mv apache-tomcat-8.5.61/ tomcat/


# the EXPOSE command will tell your future container to expose 8080 port to the outside
# 8080 is the default port for tomcat.
EXPOSE 8080

# CMD sets the first command that will run when you create containers from the resulting image.
# Here, we will start tomcat once the container is called
CMD ["/usr/local/tomcat/bin/catalina.sh", "run"]