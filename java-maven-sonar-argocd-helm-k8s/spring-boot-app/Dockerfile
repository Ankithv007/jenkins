# For Java 8, try this
# FROM openjdk:8-jdk-alpine

# For Java 11, use this
FROM adoptopenjdk/openjdk11:alpine-jre

# Define the build argument for the JAR file
ARG JAR_FILE=target/spring-boot-web.jar

# Set the working directory
WORKDIR /opt/app

# Copy the JAR file into the container
COPY ${JAR_FILE} app.jar

# Specify the command to run the JAR file
ENTRYPOINT ["java", "-jar", "app.jar"]

# Uncomment these lines if you want to use them for running the container
# sudo docker run -p 8080:8080 -t docker-spring-boot:1.0
# sudo docker run -p 80:8080 -t docker-spring-boot:1.0 
# sudo docker run -p 443:8443 -t docker-spring-boot:1.0
