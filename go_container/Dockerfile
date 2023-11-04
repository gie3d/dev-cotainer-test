FROM golang:1.21.1-alpine3.17 AS builder

WORKDIR /app

COPY . .

RUN go get
RUN go build -o bin .

# Build a smaller image
FROM alpine:3.17 AS smaller-builder
WORKDIR /app
COPY --from=builder /app/bin .

EXPOSE 9000

ENTRYPOINT [ "/app/bin" ]