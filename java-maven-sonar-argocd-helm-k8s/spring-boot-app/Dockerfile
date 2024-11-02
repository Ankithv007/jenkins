# Use the latest official OpenJDK 11 image
FROM eclipse-temurin:11-jre-alpine

# Simplify the artifact path
ARG artifact=target/spring-boot-web.jar

# Set the working directory
WORKDIR /opt/app

# Copy the built artifact to the container
COPY ${artifact} app.jar

# Entry point command
ENTRYPOINT ["java", "-jar", "app.jar"]
