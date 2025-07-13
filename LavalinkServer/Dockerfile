FROM openjdk:11-jdk-slim

# Set working directory
WORKDIR /app

# Copy everything into the container
COPY . .

# Grant permission to gradlew
RUN chmod +x ./gradlew

# Build the Lavalink jar
RUN ./gradlew shadowJar

# Set the entrypoint to run Lavalink
CMD ["java", "-Dlogback.configurationFile=logback.xml", "-jar", "build/libs/Lavalink.jar"]
