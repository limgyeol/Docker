FROM golang:1.22-alpine
WORKDIR /app
COPY main.go .
RUN go build -o main main.go && chmod +x main
EXPOSE 80
CMD ["./main"]