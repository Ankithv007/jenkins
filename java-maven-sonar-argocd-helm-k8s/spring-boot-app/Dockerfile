# Use Maven official image to build the project
FROM maven:3.8.4-openjdk-11 AS build

# Set working directory inside the container
WORKDIR /app

# Copy the Maven project files to the working directory
COPY . /app

# Build the Maven project (you can specify additional arguments here)
RUN mvn clean package

# Final image with only the built application
FROM openjdk:11-jre-slim

# Set working directory for the application
WORKDIR /app

# Copy the JAR file from the build stage
COPY --from=build /app/target/*.jar /app/app.jar

# Command to run the application
ENTRYPOINT ["java", "-jar", "/app/app.jar"]

