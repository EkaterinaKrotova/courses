FROM maven:3.5-jdk-8 AS build  
COPY . .
RUN mvn -f pom.xml clean package -DskipTests

FROM openjdk:17-jdk-alpine3.13
COPY --from=build /target/my-app-1.0-SNAPSHOT.jar ./

ENTRYPOINT ["java","-jar","/my-app-1.0-SNAPSHOT.jar"] 