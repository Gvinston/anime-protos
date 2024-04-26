FROM golang:1.22-alpine3.19
LABEL authors="vladimir"

WORKDIR /app

COPY ../.. .

RUN apk update && \
    apk add --no-cache protobuf make

RUN go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.28
RUN go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.2
RUN export PATH="$PATH:$(go env GOPATH)/bin"

CMD ["make", "-f", "scripts/Makefile", "protoc"]