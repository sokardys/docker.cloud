docker-compose.yaml: docker-compose.template.yaml $(wildcard .env)
	docker-compose -f $< config > $@

clean:
	rm docker-compose.yaml

image: docker-compose.yaml
	docker-compose $(^:%=-f docker-compose.yaml) build $(filter-out $@,$(MAKECMDGOALS))
