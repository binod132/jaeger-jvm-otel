FROM maven:3.8.4-openjdk-17-slim AS build

WORKDIR /app

# Copy the source code
COPY pom.xml /app/
COPY src /app/src

# Build the service using Maven
RUN mvn clean package -DskipTests

FROM openjdk:17-jdk-slim
WORKDIR /app
COPY --from=build /app/target/*.jar main.jar
#COPY /target/*.jar main.jar
ADD https://github.com/open-telemetry/opentelemetry-java-instrumentation/releases/latest/download/opentelemetry-javaagent.jar .
ENV JAVA_TOOL_OPTIONS "-javaagent:./opentelemetry-javaagent.jar"
CMD ["java", "-javaagent:./opentelemetry-javaagent.jar", "-jar", "main.jar"]