FROM openjdk:17-jdk-slim

# Set working directory
WORKDIR /app

# Copy everything from the kidic folder
COPY . .

# Go inside the kidic folder where gradlew is
WORKDIR /app

# Make gradlew executable
RUN chmod +x ./gradlew

# Build the project
RUN ./gradlew clean build -x test

# Expose port
EXPOSE 8080

# Run the JAR (update name if needed)
CMD ["java", "-jar", "build/libs/kidic-0.0.1-SNAPSHOT.jar"]
