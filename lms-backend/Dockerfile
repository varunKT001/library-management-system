# Use an official OpenJDK runtime as a parent image
FROM openjdk:17-jdk-slim

# Set the working directory in the container
WORKDIR /app

# Copy the Maven/Gradle wrapper files and pom.xml
COPY .mvn/ .mvn/
COPY mvnw .
COPY pom.xml .

# Copy the source code into the container
COPY src/ src/

# Package the application using Maven
RUN ./mvnw clean package -DskipTests

# Specify the command to run the app
CMD ["java", "-jar", "target/lms-backend-0.0.1-SNAPSHOT.jar"]