FROM amazoncorretto:17-alpine

WORKDIR /app
COPY build/libs/*.jar app.jar
RUN apk upgrade --no-cache && apk add --no-cache curl
EXPOSE 80

CMD ["java", "-jar", "/app/app.jar"]