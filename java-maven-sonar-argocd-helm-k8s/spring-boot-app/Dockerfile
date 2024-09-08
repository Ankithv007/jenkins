# Use a base image that includes OpenJDK 11 and Maven
FROM maven:3.8.4-openjdk-11-slim AS builder

# Install Docker in the container to enable Docker commands
USER root
RUN apt-get update && apt-get install -y docker.io

# Set the working directory for the application
WORKDIR /opt/app

# ARG for the artifact path
ARG artifact=target/spring-boot-web.jar

# Copy the application JAR file
COPY ${artifact} app.jar

# Set the ENTRYPOINT to run the Spring Boot application
ENTRYPOINT ["java", "-jar", "app.jar"]
