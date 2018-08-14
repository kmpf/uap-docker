docker-build:
	docker build \
		--network host \
		--tag kmpf/uap \
		--file Dockerfile.uap.0.0.2 \
		. # Current folder is the Docker build context

docker-build-no-cache:
	docker build \
		--network host \
		--no-cache \
		--tag kmpf/uap \
		--file Dockerfile.uap.0.0.2 \
		. # Current folder is the Docker build context

docker-run:
	@docker run \
		--interactive \
		--name uap \
		--network host \
		--rm \
		--tty \
		kmpf/uap ${ARGS}

# Push created DMS docker image to registry
docker-push:
	docker login
	docker push kmpf/uap

.PHONY: docker-build docker-build-no-cache docker-run docker-push
