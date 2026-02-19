FROM golang:1.22-alpine
WORKDIR /app
COPY main.go .
RUN apk upgrade --no-cache && apk add --no-cache curl && go mod init noah.io/ark/rest && go build app.go
EXPOSE 80
CMD ["./main"]
