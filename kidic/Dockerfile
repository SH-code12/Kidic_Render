# Use Java 21
FROM openjdk:21-jdk-slim

# Set working directory
WORKDIR /app

# Copy project files (since Dockerfile is inside kidic/)
COPY . .

# Make gradlew executable
RUN chmod +x ./gradlew

# Build the project (skip tests)
RUN ./gradlew clean build -x test

# Expose Spring Boot default port
EXPOSE 8080

# Run the jar (ensure name matches the final jar in build/libs)
CMD ["java", "-jar", "build/libs/kidic-0.0.1-SNAPSHOT.jar"]
