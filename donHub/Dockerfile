FROM maven:3.8-openjdk-17 AS build
COPY..
RUN mvn clean package -DskipTests

FROM openjdk:17-ea-11-jdk-slim-buster
COPY --from=build /target/donHub-0.0.1-SNAPSHOT.jar donHub.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","donHub.jar"]