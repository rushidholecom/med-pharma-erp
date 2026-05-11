FROM jelastic/maven:3.9.5-openjdk-21 AS build
WORKDIR /app
RUN git clone https://github.com/rushidholecom/med-pharma-erp.git

WORKDIR /order-service
COPY . .
RUN mvn clean package -DskipTests

FROM alpine/java:21-jre

WORKDIR /app

COPY --from=build /med-pharma-erp/order-service/target/order-service*.jar ./order-service.jar 
EXPOSE 8083
ENTRYPOINT ["java", "-jar", "order-service.jar"]
