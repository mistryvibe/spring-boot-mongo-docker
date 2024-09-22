FROM maven:3.9.8-amazoncorretto-11 as build
WORKDIR /app
COPY . .
RUN mvn clean package

FROM tomcat:8.0.21-jre8
copy --from=build /app/target/maven-web-application.war /usr/local/tomcat/webapps/maven-web-application.war
