FROM golang:alpine AS builder

WORKDIR /work
COPY main.go .
RUN go mod init test
RUN go build -o envweb .

FROM alpine

WORKDIR /exec
COPY --from=builder /work/envweb .
CMD ["./envweb"]
