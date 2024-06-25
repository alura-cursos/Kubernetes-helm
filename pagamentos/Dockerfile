FROM maven:3.9.6-eclipse-temurin-17-focal AS build
WORKDIR /app
COPY pom.xml .
COPY src ./src
RUN mvn clean package -DskipTests

FROM eclipse-temurin:17.0.11_9-jre-focal
WORKDIR /app
COPY --from=build /app/target/pagamentos-0.0.1-SNAPSHOT.jar .
EXPOSE 40000
CMD [ "java","-jar","pagamentos-0.0.1-SNAPSHOT.jar" ]