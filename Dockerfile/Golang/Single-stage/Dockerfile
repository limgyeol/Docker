FROM golang:1.22-alpine
WORKDIR /app
COPY main.go .
RUN apk upgrade --no-cache && apk add --no-cache curl
EXPOSE 80
CMD ["./main.go"]