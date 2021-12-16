#silence bash output &>/dev/null


# ════════════════════════════════════
CONTAINER_NAME = Example_name
# ════════════════════════════════════
IMAGE_NAME = Example2_name
# ════════════════════════════════════

# Art colors
BLU = \033[0;34m
GRN = \033[0;32m
YEL = \033[0;33m
RED = \033[0;31m
WHT = \033[0;37m
ORG = \033[38;5;202m
RESET = \033[0m

all:
	@echo ""
	@echo "Use the following parameters after the make rule for a personalized build"
	@echo ""
	@echo " -- [startdocker] Starts docker daemond"
	@echo " -- [info] display all images, containers and volumes"
	@echo " -- [build] to build all images needed"
	@echo " -- [run] to mount all images"
	@echo " -- [fast] to build and mount all images"
	@echo " -- [stop] to stop all running containers"
	@echo " -- [del] to delete all exited containers"
	@echo " -- [prune] to delete all containers, images created and volumes"
#	@echo " -- [prune_data] delet all already saved data from volumes"
	@echo " -- [re] execute prune and fast"
	@echo " -- [container] access server container"
	@echo ""

startdocker:
	open -g -a Docker &>/dev/null
	@echo "$(GRN) Docker is starting... $(RESET)"

info:
	@echo "╔════════════════════════════════════════════════════════════════════════╗"
	@echo "║ IMAGES                                                                 ║"
	@echo "╚════════════════════════════════════════════════════════════════════════╝"
	@docker images
	@echo "╔════════════════════════════════════════════════════════════════════════╗"
	@echo "║ CONTAINERS                                                             ║"
	@echo "╚════════════════════════════════════════════════════════════════════════╝"
	@docker ps -a
	@echo "╔════════════════════════════════════════════════════════════════════════╗"
	@echo "║ VOLUMES                                                                ║"
	@echo "╚════════════════════════════════════════════════════════════════════════╝"
	@docker volume ls
#	@echo "══════════════════════════════════════════════════════════════════════════"


build:
	docker build -t $(IMAGE_NAME) .

run:
	docker run -p 80:80 --name $(CONTAINER_NAME) -d $(IMAGE_NAME)
	@echo "$(GRN) ▄▄   ▄▄ ▄▄▄▄▄▄▄ "
	@echo "$(GRN)█  █ █  █       █"
	@echo "$(GRN)█  █ █  █    ▄  █"
	@echo "$(GRN)█  █▄█  █   █▄█ █"
	@echo "$(GRN)█       █    ▄▄▄█"
	@echo "$(GRN)█       █   █    "
	@echo "$(GRN)█▄▄▄▄▄▄▄█▄▄▄█    $(RESET)"
	@echo ""


fast: build run

stop:
	docker stop $$(docker ps -q)
	@echo "$(RED) ▄▄▄▄▄▄  ▄▄▄▄▄▄▄ ▄     ▄ ▄▄    ▄ "
	@echo "█      ██       █ █ ▄ █ █  █  █ █"
	@echo "█  ▄    █   ▄   █ ██ ██ █   █▄█ █"
	@echo "█ █ █   █  █ █  █       █       █"
	@echo "█ █▄█   █  █▄█  █       █  ▄    █"
	@echo "█       █       █   ▄   █ █ █   █"
	@echo "█▄▄▄▄▄▄██▄▄▄▄▄▄▄█▄▄█ █▄▄█▄█  █▄▄█$(RESET)"
	@echo ""


del:
	docker rm $$(docker ps -a -q)

prune:
	docker system prune -a -f

container:
	docker exec -it $(CONTAINER_NAME) bash

re:	stop prune fast
