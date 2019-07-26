FROM openjdk:8-alpine as build-stage

RUN apk add --no-cache git && \
    git clone https://github.com/docker-hy/spring-example-project.git

WORKDIR /spring-example-project

RUN ./mvnw package

FROM openjdk:8-alpine
EXPOSE 8080
COPY --from=build-stage /spring-example-project/target /app

RUN adduser -D app && \
    chown -R app /app

USER app

CMD java -jar ./app/docker-example-1.1.3.jar