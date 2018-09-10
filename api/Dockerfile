FROM maven:3.5.4-jdk-8 AS build

RUN mkdir /build
WORKDIR /build

COPY ./pom.xml .
RUN mvn -B -f pom.xml -s /usr/share/maven/ref/settings-docker.xml dependency:resolve

COPY ./src src
RUN mvn -B -s /usr/share/maven/ref/settings-docker.xml package -DskipTests




FROM java:8-jre-alpine

RUN mkdir /api
WORKDIR /api
COPY --from=build /build/target/ddev-0.0.1-SNAPSHOT.jar ddev.jar

RUN adduser -Dh /home/gordon gordon
USER gordon

CMD java -jar ddev.jar --spring.profiles.active=postgres
