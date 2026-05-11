FROM maven:3.8.3-openjdk-17 AS build

COPY . .

RUN mvn clean package -DskipTests

FROM eclipse-temurin:17-jre-alpine

COPY --from=build target/product-service*.jar ./product-service.jar

EXPOSE 8082

ENTRYPOINT [ "java", "-jar", "product-service.jar"]