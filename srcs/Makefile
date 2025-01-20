all: up

up:
	@docker compose -f ./srcs/docker-compose.yml up -d
down:
	@docker compose -f ./srcs/docker-compose.yml down
start:
	@docker compose -f ./srcs/docker-compose.yml start
stop:
	@docker compose -f ./srcs/docker-compose.yml stop
status:
	@docker ps

clean:
	@docker compose -f ./srcs/docker-compose.yml down --rmi all -v

fclean: clean
	@sudo rm -rf ${HOME}/data/mariadb/* && sudo rm -rf ${HOME}/data/wordpress/* && \
	echo "Removed all mariadb and wordpress data contents"

re: fclean all

.PHONY: all, clean, fclean, re