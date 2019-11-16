# 1. Build Image Environment
FROM golang AS builder
WORKDIR /go/src/github.com/Seonwhee-Finance/dockertext-greet
RUN go get -d -v github.com/urfave/cli

COPY main.go .
RUN GOOS=linux go build -a -o greet .

# 2. Service Image Environment
FROM busybox
WORKDIR /opt/greet/bin

COPY --from=builder /go/src/github.com/Seonwhee-Finance/dockertext-greet .
ENTRYPOINT ["./greet"]
