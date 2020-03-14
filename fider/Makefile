ENV_FILES=$(wildcard .env)

all: docker-compose.yaml docker-compose-restore.yaml

docker-compose.yaml: docker-compose.template.yaml $(ENV_FILES)
	docker-compose -f $< config > $@

docker-compose-restore.yaml: docker-compose-restore.template.yaml $(ENV_FILES)
	docker-compose -f $< config > $@

deploy: docker-compose.yaml
	docker stack deploy -c docker-compose.yaml $(filter-out $@,$(MAKECMDGOALS))

clean:
	rm docker-compose.yaml

image: docker-compose.yaml
	docker-compose $(^:%=-f docker-compose.yaml) build $(filter-out $@,$(MAKECMDGOALS))
