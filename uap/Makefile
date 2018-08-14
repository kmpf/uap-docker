docker-build-1.0.0:
	docker build \
		--network host \
		--tag kmpf/uap:1.0.0 \
		--file Dockerfile.uap.1.0.0 \
		. # Current folder is the Docker build context

docker-build-no-cache-1.0.0:
	docker build \
		--network host \
		--no-cache \
		--tag kmpf/uap:1.0.0 \
		--file Dockerfile.uap.1.0.0 \
		. # Current folder is the Docker build context

docker-run-1.0.0:
	@docker run \
		--interactive \
		--name uap \
		--network host \
		--rm \
		--tty \
		kmpf/uap:1.0.0 ${ARGS}

docker-build-downloads:
	docker build \
		--network host \
		--tag kmpf/uap:1.0.0+downloads \
		--file Dockerfile.uap.1.0.0-downloads \
		. # Current folder is the Docker build context

docker-build-no-cache-downloads:
	docker build \
		--network host \
		--no-cache \
		--tag kmpf/uap:1.0.0+downloads \
		--file Dockerfile.uap.1.0.0-downloads \
		. # Current folder is the Docker build context

docker-run-downloads:
	@docker run \
		--interactive \
		--name uap \
		--network host \
		--rm \
		--tty \
		kmpf/uap:1.0.0+downloads ${ARGS}

# Push created DMS docker image to registry
docker-push:
	docker login
	docker push kmpf/uap

.PHONY: docker-build docker-build-no-cache docker-run docker-push
