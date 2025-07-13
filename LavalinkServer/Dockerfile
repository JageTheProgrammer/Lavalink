FROM eclipse-temurin:17-jdk-alpine AS builder

WORKDIR /app

# Install git & unzip
RUN apk add --no-cache git unzip

# Clone Lavalink source code
RUN git clone https://github.com/lavalink-devs/Lavalink.git .

# Build Lavalink with Gradle
RUN ./gradlew shadowJar

# --- Runtime image ---
FROM eclipse-temurin:17-jre-alpine

WORKDIR /opt/Lavalink

# Copy the built Lavalink.jar from previous stage
COPY --from=builder /app/build/libs/Lavalink-*.jar ./Lavalink.jar

# Copy your config
COPY ./src/main/resources/application.yml ./application.yml

EXPOSE 2333

CMD ["java", "-Dfile.encoding=UTF-8", "-jar", "Lavalink.jar"]
