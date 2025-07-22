build:
	docker build --file ./Dockerfile --tag pwr/openfreemap .

build-c:
	docker build --no-cache --file ./Dockerfile --tag pwr/openfreemap .

down:
	docker compose -f tools/docker-compose.yml down -v

up:
	docker compose -f tools/docker-compose.yml up

login:
	docker exec -it tools-debug-1 /bin/bash
