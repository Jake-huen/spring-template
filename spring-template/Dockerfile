# Build stage
FROM gradle:7.5.1-jdk17 AS build
COPY . /app
WORKDIR /app
RUN gradle build --no-daemon


FROM openjdk:17
ARG JAR_FILE=build/libs/*.jar
COPY ${JAR_FILE} app.jar
ENTRYPOINT ["java","-jar","/app.jar"]