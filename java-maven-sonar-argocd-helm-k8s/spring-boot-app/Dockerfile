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
