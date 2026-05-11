FROM maven:3.8.3-openjdk-17 AS build

WORKDIR /app

COPY . .

RUN mvn clean package -DskipTests

FROM eclipse-temurin:17-jre-jammy

WORKDIR /app

RUN apt-get update && apt-get install -y ca-certificates

COPY --from=build /app/target/user-service*.jar user-service.jar

EXPOSE 8081

ENTRYPOINT ["java","-jar","user-service.jar"]