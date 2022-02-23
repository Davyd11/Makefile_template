# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: dpuente- <dpuente-@student.42.fr>          +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2021/10/11 17:30:37 by dpuente-          #+#    #+#              #
#    Updated: 2022/02/23 18:01:43 by dpuente-         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

#--------------------------------
NAME = a.out
#--------------------------------
#--------------------------------
SRCS = main.cpp
#--------------------------------

#silence bash output &>/dev/null

# Art colors
BLU = \033[0;34m
GRN = \033[0;32m
YEL = \033[0;33m
RED = \033[0;31m
WHT = \033[0;37m
ORG = \033[38;5;202m
RESET = \033[0m


OBJS_S					=	$(SRCS:.cpp=.o)
CXX						=	c++ --std=c++98
OPT						=	-o
RM						=	rm -f
CXXFLAGS				=	-Wall -Wextra -Werror -g3 -fsanitize=address

all:
	@echo ""
	@echo "╔═════════════════════════════════════════════════════════════════════════════╗"
	@echo "║ Use the following parameters after the <make> rule for a personalized build ║"
	@echo "╚═════════════════════════════════════════════════════════════════════════════╝"
	@echo ""
	@echo "[ UTILITIES ]"
	@echo " -- [progress] Aoutomates a commit for little changes"
	@echo "[ BUILD ]"
	@echo " -- [do] compile all files and generates $(NAME) exec"
	@echo " -- [re] Runs both <fclean> and <e> instructions"
	@echo "[ CLEAN ]"
	@echo " -- [clean] deletes all files generated during compilation"
	@echo " -- [fclean] deletes all files generated during compilation, including nokia exec"
	@echo "[ EXEC ]"
	@echo " -- [exec] runs $(NAME) executable"
	@echo ""


build_art:
	@echo "$(GRN) ▄▄▄▄▄▄▄ ▄▄   ▄▄ ▄▄▄ ▄▄▄     ▄▄▄▄▄▄  ▄▄▄ ▄▄    ▄ ▄▄▄▄▄▄▄"
	@echo "█  ▄    █  █ █  █   █   █   █      ██   █  █  █ █       █"
	@echo "█ █▄█   █  █ █  █   █   █   █  ▄    █   █   █▄█ █   ▄▄▄▄█"
	@echo "█       █  █▄█  █   █   █   █ █ █   █   █       █  █  ▄▄ "
	@echo "█  ▄   ██       █   █   █▄▄▄█ █▄█   █   █  ▄    █  █ █  █"
	@echo "█ █▄█   █       █   █       █       █   █ █ █   █  █▄▄█ █"
	@echo "█▄▄▄▄▄▄▄█▄▄▄▄▄▄▄█▄▄▄█▄▄▄▄▄▄▄█▄▄▄▄▄▄██▄▄▄█▄█  █▄▄█▄▄▄▄▄▄▄█$(RESET)"
	@echo ""

clean_art:
	@echo "$(RED)▄▄▄▄▄▄▄ ▄▄▄     ▄▄▄▄▄▄▄ ▄▄▄▄▄▄ ▄▄    ▄ ▄▄▄ ▄▄    ▄ ▄▄▄▄▄▄▄ "
	@echo "█       █   █   █       █      █  █  █ █   █  █  █ █       █"
	@echo "█       █   █   █    ▄▄▄█  ▄   █   █▄█ █   █   █▄█ █   ▄▄▄▄█"
	@echo "█     ▄▄█   █   █   █▄▄▄█ █▄█  █       █   █       █  █  ▄▄ "
	@echo "█    █  █   █▄▄▄█    ▄▄▄█      █  ▄    █   █  ▄    █  █ █  █"
	@echo "█    █▄▄█       █   █▄▄▄█  ▄   █ █ █   █   █ █ █   █  █▄▄█ █"
	@echo "█▄▄▄▄▄▄▄█▄▄▄▄▄▄▄█▄▄▄▄▄▄▄█▄█ █▄▄█▄█  █▄▄█▄▄▄█▄█  █▄▄█▄▄▄▄▄▄▄█$(RESET)"

#########
# BUILD #
#########

do:						build_art $(NAME)

$(NAME):				$(OBJS_S)
						$(CXX) $(CXXFLAGS) $(OPT) $(NAME) $(OBJS_S)

#########
# CLEAN #
#########

clean:					clean_art
						$(RM) $(OBJS_S)

fclean:					clean
						$(RM) $(NAME)

re:						fclean e

exec:
	@./$(NAME)

#########
# BUILD #
#########

fast: re exec

#########
# UTILS #
#########
progress:
	@git add . &>/dev/null
	@git commit -m "Progress"
	@git push &>/dev/null


