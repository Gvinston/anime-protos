protoc:
	protoc -I proto proto/user/user.proto --go_out=./gen/go/ --go_opt=paths=source_relative --go-grpc_out=./gen/go/ --go-grpc_opt=paths=source_relative
	protoc -I proto proto/anime/anime.proto --go_out=./gen/go/ --go_opt=paths=source_relative --go-grpc_out=./gen/go/ --go-grpc_opt=paths=source_relative
up:
	docker-compose -f $(MAKEFILE_DIR)../deployments/docker-compose.yml up -d
up_build:
	docker-compose -f $(MAKEFILE_DIR)../deployments/docker-compose.yml up -d --build