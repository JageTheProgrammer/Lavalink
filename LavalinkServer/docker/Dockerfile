FROM openjdk:17-jdk-alpine

WORKDIR /opt/Lavalink

COPY . .

RUN ./gradlew build -x test

CMD ["java", "-jar", "Lavalink.jar"]
