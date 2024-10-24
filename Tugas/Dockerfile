FROM golang:alpine AS builder

WORKDIR /go/app

COPY go.mod .         
COPY main.go .         

RUN go build -o webserver .
FROM alpine
WORKDIR /app
COPY --from=builder /go/app /app/
CMD ["./webserver"]