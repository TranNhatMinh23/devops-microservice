FROM maven as build
WORKDIR /app
COPY . .
RUN mvn install

#jdk
FROM openjdk:22-ea-16-jdk-slim-bullseye
WORKDIR /app
COPY --from=build /app/target/offers-0.0.1-SNAPSHOT.jar /app 

CMD ["java", "-jar", "offers-0.0.1-SNAPSHOT.jar"] 

