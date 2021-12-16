#silence bash output &>/dev/null


# ════════════════════════════════════
CONTAINER_NAME1 = nginx_server
# ════════════════════════════════════
#CONTAINER_NAME2 = nginx_server
# ════════════════════════════════════
#CONTAINER_NAME3 = nginx_server
# ════════════════════════════════════
# ════════════════════════════════════
# ════════════════════════════════════
IMAGE_NAME1 = server
# ════════════════════════════════════
#IMAGE_NAME2 = server
# ════════════════════════════════════
#IMAGE_NAME3 = server
# ════════════════════════════════════
# ════════════════════════════════════
# ════════════════════════════════════
IMAGE_NAME1_DIR = .
# ════════════════════════════════════
#IMAGE_NAME2_DIR = dir/example
# ════════════════════════════════════
#IMAGE_NAME3_DIR = dir/example
# ════════════════════════════════════
# ════════════════════════════════════
# ════════════════════════════════════
SHELL_TO_OPEN = bash


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
	@echo "╔═════════════════════════════════════════════════════════════════════════════╗"
	@echo "║ Use the following parameters after the <make> rule for a personalized build ║"
	@echo "╚═════════════════════════════════════════════════════════════════════════════╝"
	@echo ""
	@echo "[ UTILITIES ]"
	@echo " -- [startdocker] Starts docker daemond"
	@echo "[ INFO ]"
	@echo " -- [info] display all images, containers and volumes"
	@echo "[ BUILD ]"
	@echo " -- [build] to build all images needed"
	@echo " -- [run] to mount all images"
	@echo " -- [stop] to stop all running containers"
	@echo " -- [fast] to build and mount all images"
	@echo " -- [re] execute prune and fast"
	@echo " -- [del] to delete all exited containers"
	@echo " -- [prune] to delete all containers, images created and volumes"
#	@echo " -- [prune_data] delet all already saved data from volumes"
	@echo "[ EXEC ]"
	@echo " -- [container1] access $(CONTAINER_NAME1) container"
#	@echo " -- [container2] access $(CONTAINER_NAME2) container"
#	@echo " -- [container3] access $(CONTAINER_NAME3) container"
	@echo ""

startdocker:
	@open -g -a Docker &>/dev/null
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
	docker build -t $(IMAGE_NAME1) $(IMAGE_NAME1_DIR)
#	docker build -t $(IMAGE_NAME2) $(IMAGE_NAME2_DIR)
#	docker build -t $(IMAGE_NAME3) $(IMAGE_NAME3_DIR)

run:
#	══════════════════════════════════════════════════════════════════════════
#	docker-compose -f srcs/docker-compose.yaml up -d
#	══════════════════════════════════════════════════════════════════════════
	docker run -p 80:80 --name $(CONTAINER_NAME1) -d $(IMAGE_NAME1)
#	══════════════════════════════════════════════════════════════════════════

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

container1:
	docker exec -it $(CONTAINER_NAME1) $(SHELL_TO_OPEN)
#container2:
#	docker exec -it $(CONTAINER_NAME2) bash
#container3:
#	docker exec -it $(CONTAINER_NAME3) bash

re:	stop prune fast