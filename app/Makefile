.PHONY: all
all:
	@echo "**********************************************************"
	@echo "**                    app build tool                    **"
	@echo "**********************************************************"


install:
	go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.28
	go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.2
	go install github.com/sqlc-dev/sqlc/cmd/sqlc@latest

sqlc-gen:
	sqlc generate

protoc:
	protoc --go_out=internal/infra/left/grpc internal/infra/left/grpc/proto/user.proto
	protoc --go-grpc_out=require_unimplemented_servers=false:internal/infra/left/grpc internal/infra/left/grpc/proto/service.proto

.PHONY: test
test:
	go test -race -v ./internal/...
