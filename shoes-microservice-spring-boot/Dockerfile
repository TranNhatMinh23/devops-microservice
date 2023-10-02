FROM maven as build
WORKDIR /app
COPY . .
RUN mvn install

#jdk
FROM openjdk:Always22-ea-16-jdk-slim-bullseye
WORKDIR /app
COPY --from=build /app/target/shoes-0.0.1-SNAPSHOT.jar /app 

EXPOSE 1002

CMD ["java", "-jar", "shoes-0.0.1-SNAPSHOT.jar"] 
