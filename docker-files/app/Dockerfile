FROM maven:3.9-eclipse-temurin-17 AS build


RUN git clone https://github.com/hkhcoder/vprofile-project.git /app
WORKDIR /app
RUN mvn install -DskipTests


FROM tomcat:10-jdk17


RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=build /app/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war


EXPOSE 8080
CMD ["catalina.sh", "run"]
