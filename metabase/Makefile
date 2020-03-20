docker-compose.yaml: docker-compose.template.yaml $(wildcard .env)
	docker-compose -f $< config > $@

# --no-cache to force image
image: docker-compose.yaml
	docker-compose $(^:%=-f docker-compose.yaml) build $(filter-out $@,$(MAKECMDGOALS))

clean:
	rm docker-compose.yaml