docker-compose.yaml: docker-compose.template.yaml $(wildcard .env)
	docker-compose -f $< config > $@

clean:
	rm docker-compose.yaml

reset:
	docker stack rm play_lightnite

deploy:
	docker stack deploy --with-registry-auth -c docker-compose.yaml play_lightnite
