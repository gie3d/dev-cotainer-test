IMAGE=mariadb-sms
TAG=latest

build:
	docker build . -t "${IMAGE}:${TAG}"

run: build
	docker run -d -p 3307:3306 --volume ./data:/var/lib/mysql  --name="${IMAGE}" "${IMAGE}:${TAG}"

stop: 
	docker stop ${IMAGE}
	docker rm ${IMAGE}