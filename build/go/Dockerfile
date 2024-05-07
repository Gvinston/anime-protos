FROM golang:1.22-alpine3.19
LABEL authors="vladimir"

WORKDIR /app

COPY ../.. .

RUN apk update && \
    apk add --no-cache protobuf make

RUN	go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.27.1
RUN	go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.1.0
RUN	go install github.com/grpc-ecosystem/grpc-gateway/v2/protoc-gen-grpc-gateway@v2.5.0
RUN	go install github.com/grpc-ecosystem/grpc-gateway/v2/protoc-gen-openapiv2@v2.5.0
RUN	go install github.com/envoyproxy/protoc-gen-validate@latest
RUN	go install github.com/grpc-ecosystem/grpc-gateway/protoc-gen-swagger@latest
RUN go mod tidy
RUN export PATH="$PATH:$(go env GOPATH)/bin"

CMD ["make", "-f", "scripts/Makefile", "protoc"]