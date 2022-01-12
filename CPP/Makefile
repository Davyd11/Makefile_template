# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: dpuente- <dpuente-@student.42.fr>          +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2021/10/11 17:30:37 by dpuente-          #+#    #+#              #
#    Updated: 2022/01/12 16:22:06 by dpuente-         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

#--------------------------------
NAME = a.out
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

SRCS					=	main.cpp \


OBJS_S					=	$(SRCS:.cpp=.o)
CXX						=	c++ --std=c++98
OPT						=	-o
RM						=	rm -f
CXXFLAGS				=	-Wall -Wextra -Werror -g3 -fsanitize=address

all:
	@echo ""
	@echo " -- [e] compile all files and generates nokia exec"
	@echo " -- [clean] deletes all files generated during compilation"
	@echo " -- [fclean] deletes all files generated during compilation, including nokia exec"
	@echo " -- [re] Runs both <fclean> and <e> instructions"
	@echo " -- [progress] Aoutomates a commit for little changes"
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

e:						build_art $(NAME)

$(NAME):				$(OBJS_S)
						$(CXX) $(CXXFLAGS) $(OPT) $(NAME) $(OBJS_S) 

clean:					clean_art
						$(RM) $(OBJS_S)

fclean:					clean
						$(RM) $(NAME)

progress:
	@git add . &>/dev/null
	@git commit -m "Progress from $(date +"%d-%m-%Y --> %T")"
	@git push &>/dev/null

re:						fclean e
