# to run spring boot app : mvn spring-boot:run
# run springboot in dev mode : mvn spring-boot:run -Dspring-boot.run.profiles=dev
# install maven : sudo apt install maven
# install java : sudo apt install openjdk-11-jdk
FROM maven:3.8.1-openjdk-11-slim AS build
COPY src /home/app/src
COPY pom.xml /home/app
RUN mvn -f /home/app/pom.xml clean package -DskipTests
FROM openjdk:11-jre-slim
COPY --from=build /home/app/target/*.jar /usr/local/lib/app.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","/usr/local/lib/app.jar"]


