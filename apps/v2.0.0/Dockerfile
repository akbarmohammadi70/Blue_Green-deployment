FROM golang:latest as builder
MAINTAINER "Akbar Mohammadi"

WORKDIR /var/
COPY . /var/

RUN go build -o main /var/main.go

FROM alpine
WORKDIR /var/
COPY --from=builder /var/main /var/
CMD ["./main"]
               