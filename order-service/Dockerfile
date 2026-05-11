FROM jelastic/maven:3.9.5-openjdk-21 AS build
WORKDIR /app
RUN git clone https://github.com/rushidholecom/med-pharma-erp.git

WORKDIR /order-service

RUN mvn clean package -DskipTests

FROM openjdk:21-jre-slim

WORKDIR /app

COPY --from=build /app/order-service/target/order-service-0.0.1-SNAPSHOT.jar order-service.jar 
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "order-service.jar"]
