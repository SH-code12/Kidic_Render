# Use an OpenJDK base image
FROM openjdk:17-jdk-slim

# Set the working directory inside the container
WORKDIR /app

# Copy Gradle wrapper and build files
COPY gradlew .
COPY gradle/ gradle/
COPY build.gradle .
COPY settings.gradle .

# Give permission to gradlew
RUN chmod +x ./gradlew

# Copy the rest of the project
COPY . .

# Build the project (skip tests for speed)
RUN ./gradlew clean build -x test

# Expose port 8080
EXPOSE 8080

# Run the JAR file (update if your jar name is different)
CMD ["java", "-jar", "build/libs/kidic-0.0.1-SNAPSHOT.jar"]
