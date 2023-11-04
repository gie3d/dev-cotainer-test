NAME="Brian"
IMAGE=go-containerized
TAG=latest

hello:
	echo "hello ${NAME}!"

world: hello
	echo "this is a chained command"

helloworld: hello world
	echo "test"

build:
	docker build . -t "${IMAGE}:${TAG}"

run: build
	docker run --name=go_container1 -e PORT=9000 -p 9000:9000 "${IMAGE}:${TAG}"

publish: build
	docker push "${IMAGE}:${TAG}"
