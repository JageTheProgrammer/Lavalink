# Use OpenJDK 17, required for Lavalink v4
FROM openjdk:17-slim

# Set working directory
WORKDIR /app

# Copy everything
COPY . .

# Make gradlew executable
RUN chmod +x ./gradlew

# Build Lavalink using Spring Boot (not shadowJar!)
RUN ./gradlew bootJar

# Run the Lavalink JAR
CMD ["java", "-Dlogback.configurationFile=logback.xml", "-jar", "build/libs/Lavalink.jar"]
