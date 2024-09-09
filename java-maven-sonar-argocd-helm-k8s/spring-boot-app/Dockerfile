# Use the base image with Java 11
FROM adoptopenjdk/openjdk11:alpine-jre

# Set the working directory inside the container
WORKDIR /opt/app

# Copy the JAR file from the build context to the container
COPY target/spring-boot-web.jar app.jar

# Define the command to run the JAR file
ENTRYPOINT ["java", "-jar", "app.jar"]
