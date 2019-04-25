docker-compose.yaml: docker-compose.template.yaml $(wildcard .env)
	docker-compose -f $< config > $@

image:
	docker-compose $(^:%=-f docker-compose.yaml) build

clean:
	rm docker-compose.yaml