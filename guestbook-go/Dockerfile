FROM golang:1.16-alpine AS builder
WORKDIR /app
COPY . .
RUN go mod download
RUN go build -o guestbook-go

FROM alpine:latest
WORKDIR /root/
COPY --from=builder /app/guestbook-go .
EXPOSE 8080
CMD ["./guestbook-go"]
