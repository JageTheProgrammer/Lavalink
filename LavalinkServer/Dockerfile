FROM eclipse-temurin:17-jdk-alpine

WORKDIR /opt/Lavalink

RUN apk add --no-cache curl

COPY ./Lavalink.jar ./Lavalink.jar
COPY ./src/main/resources/application.yml ./application.yml

EXPOSE 2333

CMD ["java", "-Dfile.encoding=UTF-8", "-jar", "Lavalink.jar"]
