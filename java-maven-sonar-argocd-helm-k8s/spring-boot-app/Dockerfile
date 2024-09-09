# Use the base image for Java 11 with Alpine Linux
FROM adoptopenjdk/openjdk11:alpine-jre

# Set working directory
WORKDIR /opt/app

# Define the build-time argument for the JAR file path
ARG JAR_FILE=target/spring-boot-web.jar

# Copy the JAR file from the build context to the working directory in the container
COPY ${JAR_FILE} app.jar

# Define the command to run the application
ENTRYPOINT ["java", "-jar", "app.jar"]
